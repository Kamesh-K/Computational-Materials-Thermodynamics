# Computational Materials Thermodynamics

# Introduction to ThermoCalc

### Basic Commands overview

1. List of commands can be obtained using the "?" command 
2. All the commands are case insensitive 
3. Abbreviations are present for commands
    1. goto_model has the same meaning as go, g_m or g 
    2. Underscore has the same meaning as hyphen - g_m and g-m mean the same 
4. Command parameters can be entered in same line or separately 
5. Default value for a parameter is set using ",," just after the set command without a space 

### Commonly used modules

Macrofiles are used to save and rerun sets of commands. Replace exit in the log file by set_interactive and use the load macro option in the SYS module 

1. SYS: System Utilities 
    1. set_log_file [file] [comment]
    2. macro_file_open [file]
    3. set_tc_options [options]
    4. goto_module [name]

2. Database Retrieval module - Mainly to setup the database for further calculations 
    1. goto_module → DATABASE_RETRIEVAL
    2. switch_database [database]
        1. Switching the database for carrying out calculations 
    3. append_database [database]
        1. Appending to compatible database to carry out calculations 
    4. define_system [components]
        1. Defining the components or the elements which we are considering for calculation will be shown 
        2. From the list of options we will add some components to define the system 
    5. get_data
    6. reject [option]
    7. restore [option]
    8. database_information

3. Gibbs Energy System (Use go g-e-s)
    1. list_data [screen|file] 
        1. All the gibbs energy systems will be defined and output in the screen 
    2. list_phase_data [phase]
    3. amend_phase_description [phase] [option]

4. Poly Module (go POLY_3) 
    1. Local and Global Minimization strategies are used 
        1. This is important for the case of miscibility gaps 
        2. POLY_3 switches between local and global minimization 
    2. Function minimization is one of the important tasks which is performed by POLY_3 module 
    3. set_condition [C+2 conditions]
    4. compute_equilibrium 
        1. Computes the eqlbrm of the state and the values can be viewed using the Show command 

5. Show_value command 
    1. To display the variables values in the console 
    2. G and G_M are two different things.
        1. G refers to the Gibbs energy of the component 
        2. G_M is the molar gibbs energy 
    3. The suffixes will be different, refer to the table attached in the ppt 
    4. List Equilibrium 
        1. To list the equilibrium which is established
6. Set_axis_variable 
    1. Variation of one of the variables - You need to set the condition on a variable with upper and lower bound 
    2. Default increment is used if we don't want to change anything 
    3. After setting the axis we can save the data 
        1. Save command is used to save the same 
    4. step is used after setting the axes of the diagram 
7.  POST processing - POST Command 
    1. SET_DIAGRAM_AXIS - s-d-a
        1. Input of Axis and the corresponding variable 
        2. Use the PLOT_DIAGRAM to plot the diagram 
        3. To set the temperature axis to celsius you can use T-C 
        4. Use the plot command to plot the diagram
    2. Set reference State - s-re-s 
        1. s-d-a y GMR(*) gives us the plots in different colors
    3. make_experimental_datafi - Makes a datafile of the processed data  

    # Magnetic Contribution

    1. G-E-S Module 
        1. Append Phase Description - amend_phase_description [phase] [option]
            1. REMOVE_ADDITIONS - removes all the additions to the mentioned phase 
            2. We can switch back to poly3 module and calculate the Cp 
            3. We have re-establish the equilibrium and then do the post processing required 
    2. Poly
        1. Compute equilibrium 
        2. save before stepping, make sure the files of ferro and para are different
