# DRV8305_FOC_Tuning

Use LA2b to identify Rs Ls

set tuning parameters to NULL
#if (USER_MOTOR == my_5208Gimbal_Motor)                  // Name must match the motor #define
#define USER_MOTOR_TYPE                 MOTOR_Type_Pm  // Motor_Type_Pm (All Synchronous: BLDC, PMSM, SMPM, IPM) or Motor_Type_Induction (Asynchronous ACI)
#define USER_MOTOR_NUM_POLE_PAIRS       (6)            // PAIRS, not total poles. Used to calculate user RPM from rotor Hz only
#define USER_MOTOR_Rr                   (NULL)         // Induction motors only, else NULL
#define USER_MOTOR_Rs                   (NULL)     // Identified phase to neutral resistance in a Y equivalent circuit (Ohms, float)
#define USER_MOTOR_Ls_d                 (NULL)  // For PM, Identified average stator inductance  (Henry, float)
#define USER_MOTOR_Ls_q                 (NULL)  // For PM, Identified average stator inductance  (Henry, float)
#define USER_MOTOR_RATED_FLUX           (NULL)         // Identified TOTAL flux linkage between the rotor and the stator (V/Hz)
#define USER_MOTOR_MAGNETIZING_CURRENT  (NULL)         // Induction motors only, else NULL
#define USER_MOTOR_RES_EST_CURRENT      (0.5)          // During Motor ID, maximum current (Amperes, float) used for Rs estimation, 10-20% rated current
#define USER_MOTOR_IND_EST_CURRENT      (-0.5)         // During Motor ID, maximum current (negative Amperes, float) used for Ls estimation, use just enough to enable rotation
#define USER_MOTOR_MAX_CURRENT          (2.0)         // CRITICAL: Used during ID and run-time, sets a limit on the maximum current command output of the provided Speed PI Controller to the Iq controller
#define USER_MOTOR_FLUX_EST_FREQ_Hz     (20.0)         // During Motor ID, maximum commanded speed (Hz, float), ~10% rated

Then use lab3a to identify bias voltage and current


