1. Download the kali linux release from this [link](https://github.com/RoganDawes/P4wnP1_aloa/releases 
2. Download the raspberry pi imager from the official site. Install and run the imager
3. Select the OS >> Custom OS >> Locate the kali linux release >> and select ok
4. Plugin the Micro SD Card (preferably 32GB) and select it as destination to write the image.
5. Confirm and let it install (and then verify) the Kali Linux OS in that card. 





//Log something to internal console
console.log("HID testscript");

layout("US"); //set US layout

// function to type fast
function typefast(text) {
    typingSpeed(50,100);
  // typingSpeed(0, 0);
  type(text);
    pause(2,3);
}

// function to type medium
function typemed(text) {
    typingSpeed(50,400);
  // typingSpeed(0, 0);
  type(text);
    pause(1,5);
}
// functin to type slow
function typeslow(text) {
    typingSpeed(40,1000);
  // typingSpeed(0, 0);
  type(text);
    pause(5,10);
}

// function to superfast
function typesufast(text) {
  typingSpeed(0, 0);
  type(text);
    pause(1,2);
}

// delay function
function pause(min, max) {
  delay((Math.floor(Math.random() * (max - min + 1)) + min) * 1000);
}

// view other screen
function altab(min, max) {
  pause(min, max);
  press("alt tab");
  moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
  pause(min, max);
  press("alt tab");
  moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
  pause(min, max);
}

typefast("IFS_DIR=");
typeslow("'${1:-$(pwd)}'\n\n");
pause(7,15);

typesufast("# ------------- \n");
typefast("# Set the current library where the programs will be compiled. \n");
typesufast("# -------------  \n\n");
altab(5,7);

typefast("CUR_LIB=");
typeslow("'RAVI' \n\n");
pause(7,15);

typesufast("# -------------  \n");
typefast("# Set the source physical file names. \n");
typesufast("# ------------- \n\n");
altab(5,7);

typemed("DDS_SRC='QDDSSRC' \n");
pause(3,5);
typemed("RPGLE_SRC='QRPGLESRC' \n");
pause(3,5);
typemed("CL_SRC='QCLLESRC' \n");
pause(3,5);
typemed("SQL_SRC='QSQLSRC' \n");
pause(3,5);
typemed("TXT_SRC='QTXTSRC' \n");
pause(3,5);
typemed("MOD_SRC='QMODSRC' \n");
pause(3,5);
typemed("SRC_TXT='Sources file' \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# Set application name \n");
typefast("APPLICATION=");
typeslow("'DevOps on Git' \n\n");
pause(5,10);

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

altab(10,20);
typesufast("# ------------- \n");
typefast("# Execute the command by setting the library first \n");
typesufast("# ------------- \n");

typeslow("exec_cmd(){ \n");
typefast("echo $1 \n");
typefast("output=$");
typeslow("(qsh -c 'liblist -a $CUR_LIB ; system '$1'') \n");
typeslow("if [ -n '$2' ];");
typefast("then \n");
typefast("echo -e ");
typeslow("'$1$output' > '$IFS_DIR/logs/$2.log' \n");
typefast("fi \n");
typefast("} \n\n");
altab(20,30);

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typesufast("# ------------- \n");
typefast("# Copy all the sources to the respective source files. \n");
typesufast("# ------------- \n");

typemed("copy_source(){ \n");
typefast("# For every file in the current IFS directory \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typefast("do \n");
typefast("# Get the name of the member alone. \n");
typemed("justname=$");
typeslow("(basename '$FILE') \n");
typemed("member=");
typeslow("'${justname%.*}' \n");
typefast("# Get the source type. \n");
typemed("ext=");
typeslow("'${justname##*.}' \n\n");
altab(20,30);

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typefast("# If Display file source... \n");
typefast("if");
typeslow("[[ $ext == 'dspf' ]];");
typefast("then \n");
typefast("echo -e");
typeslow("'=========== Copying $member =============' \n");
typemed("SRC_FILE= \n");
typeslow("$DDS_SRC \n");
typemed("SRC_TYP=");
typeslow("'DSPF' \n\n");

typefast("# If Physical File Source... \n");
typemed("elif");
typeslow("[[ $ext == 'pf' ]];");
typefast("then \n");
typefast("echo -e ");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$DDS_SRC \n");
typemed("SRC_TYP=");
typeslow("'PF' \n\n");
altab(20,30);

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# If Printer Files... \n");
typemed("elif");
typeslow("[[ $ext == 'prtf' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$DDS_SRC \n");
typemed("SRC_TYP=");
typeslow("'PRTF' \n\n");
altab(20,30);

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# If RPGLE source... \n");
typemed("elif");
typeslow("[[ $ext == 'rpgle' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$RPGLE_SRC \n");
typemed("SRC_TYP=");
typeslow("'RPGLE' \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# If SQLRPGLE source... \n");
typemed("elif");
typeslow("[[ $ext == 'sqlrpgle' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$RPGLE_SRC \n");
typemed("SRC_TYP=");
typeslow("'SQLRPGLE' \n\n");
altab(20,30);

typefast("# If CLLE source... \n");
typemed("elif");
typeslow("[[ $ext == 'clle' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$CL_SRC \n");
typemed("SRC_TYP=");
typeslow("'CLLE' \n\n");
altab(20,30);

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# If SQL source... \n");
typemed("elif");
typeslow("[[ $ext == 'sql' ]];");
altab(20,30);
typefast("then \n");
typefast("echo -e");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$SQL_SRC \n");
typemed("SRC_TYP=");
typeslow("'SQL' \n\n");

typefast("# If plain texts or copy books... \n");
typemed("elif");
typeslow("[[ $ext == 'txt' ]];");
typefast("then \n");
altab(20,30);
typefast("echo -e");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$TXT_SRC \n");
typemed("SRC_TYP=");
typeslow("'TXT' \n\n");

typefast("# If Shell scripts... \n");
typemed("elif");
typeslow("[[ $ext == 'sh' ]];");
typefast("then \n");
typefast("echo");
typemed("'=========== Copying $member =============' \n");
typemed("SRC_FILE=");
typeslow("$TXT_SRC \n");
typemed("SRC_TYP=");
typeslow("'SH' \n");
typefast("fi \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("exec_cmd");
typemed("'CHGATR OBJ('$FILE') ATR(*CCSID) VALUE(819)' \n");
typefast("exec_cmd ");
typemed("'CPYFRMSTMF FROMSTMF('$FILE') TOMBR('/QSYS.lib/$CUR_LIB.lib/$SRC_FILE.file/$member.mbr') MBROPT(*REPLACE)' \n");
typefast("exec_cmd");
typemed(" 'CHGPFM FILE($CUR_LIB/$SRC_FILE) MBR($member) SRCTYPE($SRC_TYP) TEXT('$APPLICATION')' \n\n");
typefast("done \n\n");
typesufast("} \n\n");

typesufast("# ------------- \n");
typefast("# Compile the sources \n");
typesufast("# ------------- \n");

typefast("compile_source(){ \n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# Compile the PF \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
typemed("[[ $ext == 'pf' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Building PF - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd");
typemed("'CRTPF FILE($CUR_LIB/$member) SRCFILE($CUR_LIB/$DDS_SRC)' $member \n\n");
typefast("fi \n");
typefast("done \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# Compile the Display Files \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
typemed("[[ $ext == 'dspf' ]];");
typefast("then \n");

typefast("echo -e");
typemed("'=========== Building DSPF - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd");
typemed("'CRTDSPF FILE($CUR_LIB/$member) SRCFILE($CUR_LIB/$DDS_SRC)  REPLACE(*YES)' $member \n\n");
typefast("fi \n");
typefast("done \n\n");

typefast("# Compile the Printer Files \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
typemed("[[ $ext == 'prtf' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Building PRTF - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd");
typemed("'CRTPRTF FILE($CUR_LIB/$member) SRCFILE($CUR_LIB/$DDS_SRC)  REPLACE(*YES)' $member \n\n");
typefast("fi \n");
typefast("done \n\n");

typefast("# Compile SQL \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
typemed("[[ $ext == 'sql' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Building SQL - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd");
typemed("'RUNSQLSTM SRCFILE($CUR_LIB/$SQL_SRC) SRCMBR($member) COMMIT(*NONE)  MARGINS(145) DFTRDBCOL(HOMESOFT) DBGVIEW(*SOURCE)' $member  \n\n"
);
typefast("fi \n");
typefast("done \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# Compile RPGLE \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
typemed("[[ $ext == 'rpgle' ]];");
typefast("then \n");
typefast("echo -e");
typemed("'=========== Building RPGLE - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd");
typemed("'CRTBNDRPG PGM($CUR_LIB/$member) DFTACTGRP(*NO)  DBGVIEW(*SOURCE) REPLACE(*YES)' $member \n");
typefast("fi \n");
typefast("done \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("# Compile SQLRPGLE \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typemed("[[ $ext == 'sqlrpgle' ]];");
typefast("then \n");
typefast("echo -e");
moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typemed("'=========== Building SQLRPGLE - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd ");
typemed("'CRTSQLRPGI OBJ($CUR_LIB/$member) SRCFILE($CUR_LIB/$RPGLE_SRC) COMMIT(*NONE) DBGVIEW(*SOURCE) REPLACE(*YES)' $member'\n");
typefast("fi \n");
typefast("done \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typefast("# Compile CLLE \n");
typemed("for FILE in");
typeslow("'$IFS_DIR'/* \n");
typefast("do \n");
typemed("ext='${FILE##*.}' \n");
typefast("if");
typemed("[[ $ext == 'clle' ]];");
typefast("then \n");
typefast("echo -e");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typemed("'=========== Building CLLE - $FILE =============' \n");
typemed("filename=$(basename '$FILE') \n");
typefast("member=");
typeslow("'${filename%.*}' \n");
typefast("exec_cmd");
typemed("'CRTBNDCL PGM($CUR_LIB/$member) SRCFILE($CUR_LIB/$CL_SRC)  DFTACTGRP(*NO) ACTGRP(*CALLER) DBGVIEW(*SOURCE)' $member  \n\n");
typefast("fi \n");
typefast("done \n\n");
typesufast("} \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typesufast("# -------------  \n");

typefast("# Create the required source files \n");
typesufast("# -------------  \n");
typefast("create_source_files(){ \n");
typefast("system ");
typemed("'CRTLIB LIB($CUR_LIB) TYPE(*TEST) TEXT('$CUR_LIB library')' \n");
typefast("system ");
typemed("'CRTSRCPF FILE($CUR_LIB/$DDS_SRC) RCDLEN(140) TEXT('$DDS_SRC $SRC_TXT')' \n");
typefast("system ");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typemed("'CRTSRCPF FILE($CUR_LIB/$RPGLE_SRC) RCDLEN(140) TEXT('$RPGLE_SRC $SRC_TXT')' \n");
typefast("system ");
typemed("'CRTSRCPF FILE($CUR_LIB/$CL_SRC) RCDLEN(140) TEXT('$CL_SRC $SRC_TXT')' \n");
typefast("system ");
typemed("'CRTSRCPF FILE($CUR_LIB/$SQL_SRC) RCDLEN(140) TEXT('$SQL_SRC $SRC_TXT')' \n");
typefast("system ");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);
typemed("'CRTSRCPF FILE($CUR_LIB/$TXT_SRC) RCDLEN(140) TEXT('$TXT_SRC $SRC_TXT')' \n");
typefast("system ");
typemed("'CHGPDMDFT USER($CUR_LIB) CRTBCH(*NO) EXITENT(*NO) CHGTYPTXT(*NO)' \n");
typemed("PATH=/QOpenSys/pkgs/bin:$PATH \n");
typesufast("} \n\n");

typesufast("# -------------#  \n");
typesufast("# -------------# \n");
typesufast("#              #  \n");
typefast("# start of the main logic # \n");
typesufast("#              #  \n");
typesufast("# -------------#  \n");
typesufast("# -------------# \n\n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);

typefast("echo -e \n");
typemed("'|=== Starting to copy the programs for $APPLICATION ===|' \n");
typefast("mkdir -p logs \n\n");

 typefast("# STEP 1: CREATE THE TARGET LIBRARY AND SOURCE FILE ----------------- \n ");
typemed("create_source_files \n\n");
typefast("# STEP 2: COPY THE SOURCES FROM IFS INTO THE TARGET LIBRARY -------- \n");
typemed("copy_source \n\n");
typefast("# STEP 3: COMPILE THE SOURCES INTO THE TARGET LIBRARY -------------- \n");
typemed("compile_source \n\n");

typefast("echo -e'|=======================|' \n");
typemed("echo  -e'| Program build completed, please check log files if you want|' \n");
typemed("echo  -e'|               $IFS_DIR/logs                                |' \n");
typefast("echo -e'|=======================|' \n");

moveStepped(Math.random() * 256 - 128, Math.random() * 256 - 128);