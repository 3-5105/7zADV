UTF-8 encoding format; Please turn off automatic line wrapping and expand the viewer window as much as possible for the best reading experience

1.Introduction
This file is the source code file description for 7zADV, from 3-5105
7zADV is a project that converts the single file command-line version of 7-zip (version 23.01, from October 28, 2023) (usually named 7za. exe) into a DLL (dynamic link library format)
The 7-zip here refers to an open-source compression software created by Igor Pavlov (RU) with extremely high compression ratios

7-zip Simplified Chinese official website
https://sparanoid.com/lab/7z/

7-zip English official website
https://7-zip.org/

The compiler is VC++6.0




2.Important file directory description:
([.] represents the current directory, [..] represents the higher-level directory, and [*] represents a wildcard character)

.\Asm 				assembly source code

.\* C 				C language source code

.\* CPP 			C++ source code

.\Alone 			Project Name: Alone, generate 7zan. exe, the original 7-zip single file command line project
				You only need this file to use all the core functions of 7-zip from the command line, which is the unmodified original version
				.\Alone\CPP\7zip\Bundles\Alone is the project main folder

.\7zADV_ MiniChange		Project Name: 7zADV_ MiniChange, generate 7zADV.dll, minimize modifications to the Alone project to make it a dynamic link library
				Compared to the Alone project, only Main.cpp and MainAr.cpp have been modified and the modified content has been detailed
				API Description:
				main (char * cmdLine)
				Command line parameters for cmdLine: 7zan.exe
				For specific command line parameters, please refer to Parameter Description (Chinese). txt or Parameter Description (English). txt
				This dynamic link library has an export function main, which takes a char * pointer to a string and processes it
				This project processes the string in the same way as the Alone project, so its content is the command line parameter of 7zan. exe
				.\7zADV_ MiniChange\CPP\7zip\Bundles\7zADV_ MiniChange is the project main folder

.\7zADV_ Complete		project name: 7zADV_ Complete, generate 7zADV.dll, in 7zADV_ Make modifications based on the MiniChange project
				Optimized for DLLs, mainly removing code output to the screen, reducing volume and accelerating speed
				Usage and 7zADV_ The MiniChange project is the same
				This project should be used instead of 7zADV in software that needs to be released_ MiniChange Engineering
				.\7zADV_ Complete\CPP\7zip Bundles\7zADV_Complete is the project main folder

.\Demo(3_5105) 			C++ sample call

.\Shell 			Shell Tool


3、 Other
This project is based on Igor Pavlov's 7-zip
New person on the road, welcome any valuable suggestions and criticisms
The English version is machine translated and may conflict with the original meaning. The simplified Chinese version shall prevail
Previously, projects similar to this project had already been issued, such as 7-zip32.dll from Akita (JP), which is more complete than this project
However, due to the inability to find updates after 2010 and the inability to use new features such as multithreading, this project was created