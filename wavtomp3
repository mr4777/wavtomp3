@echo off
setlocal enabledelayedexpansion

chcp 65001

if not exist "./converted" mkdir "./converted"

FOR /F "usebackq tokens=*" %%a IN (`dir /b /a`) DO ( 
  set str=%%a
  IF "!str:~-4!"==".wav" (
    ffmpeg -i "%%a" -b:a 320k "!str:~0,-4!.mp3"
    if errorlevel 1 call :stop
    move "%%a" "./converted"
  )
)

exit

:stop
echo ERROR!!
pause
exit
