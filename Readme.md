# 1. Todo 20230209

| ACTIVITY                                                     | STARTING DATE | EXPECTED FINISH DATE | EXPECTED EFFORT (days) | REAL FINISH DATE | NOTE |
| ------------------------------------------------------------ | ------------- | -------------------- | ---------------------- | ---- | ---- |
| Have a look of the point 3, for the general flow             | 2023-02-09 | 2023-02-09 | 1 | 2023-02-09 |      |
| 4.3: Change the order using to the document and add for MFP  | 2023-02-15 | 2023-02-16 | 2 | 2023-02-24       |  |
| 4.4: Format and store correctly the devicesV5.json and remotesV5.json | 2023-02-15 | 2023-02-20 | 4 | 2023-02-20 |  |
| 4.5 Correctly format the json signal and add for MFP | 2023-02-17 | 2023-02-20 | 2 | 2023-02-24 | See 5.4 Telemetry on this document |
| 4.7 Move you storage path to /etc/yokis/v5 and /etc/yokis/json | 2023-02-24 | 2023-03-02 | 3 | 2023-02-20 |      |
| 5.1.3 Check that the command refresh correctly update the devicesV5.json | 2023-02-21 | 2023-02-22 | 2 |      | In progress ... |
| 5.1.4 Check taht the command update correctly update the devicesV5.json | 2023-02-23 | 2023-02-24 | 2 |      | In progress ... |
| 5.4.1 Re-format the telemetry states signal | 2023-02-17 | 2023-02-20 | 2 | 2023-03-01 |      |
| 5.4.2 Format remotes signal | 2023-02-21 | 2023-02-21 | 1 | 2023-03-01 |      |
| 5.4.3 Send signal after a new config is added | 2023-02-22 | 2023-02-23 | 2 | 2023-02-22 |      |
| 5.5 Use the signal from button | 2023-02-24 | 2023-02-24 | 1 | 2023-02-20 |      |
| 5.6 Send signal to drive leds | 2023-02-24 | 2023-02-24 | 1 | 2023-02-20 |      |
| 5.7 Post data | 2023-03-01 | 2023-03-02 | 2 | 2023-02-23 | without “uid” returned by the getinfo, only "serialId" |
| As discussed please remove all the deamons not use within the UP scope | 2023-03-03 | 2023-03-07 | 3 | 2023-02-17 |      |
|               |                      |                        |          |      |      |

# 2. Gantt

## 2.1. Analysis

```mermaid
gantt
	title 20230209-TaskList
	dateFormat  YYYY-MM-DD

  axisFormat %-m/%-d
	excludes weekends saturday,sunday, 2023-02-27, 2023-02-28

	section SPEC
		read 20230209-TaskList.pdf: crit, active, spec1, 2023-02-09, 1d
	section CODEBASE
		upgrade codebase and branch: crit, base1, after spec1, 3d
	section Todo
		Have a look of the point 3, for the general flow: active, todo3, 2023-02-09, 1d
		4.3 Change the order using to the document and add for MFP (SPE-CommandsOrders.xlsx/UP_to_V5_Order): todo43, after base1, 2d
		4.4 Format and store correctly the devicesV5.json and remotesV5.json: todo44, after base1, 4d
		4.5 Correctly format the json signal and add for MFP (See 5.4 Telemetry on this document): todo45, after todo43, 2d
		4.7 Move you storage path to /etc/yokis/v5 and /etc/yokis/json: todo47, after todo543, 3d
		5.1.3 Check that the command refresh correctly update the devicesV5.json: todo513, after todo44, 2d
		5.1.4 Check taht the command update correctly update the devicesV5.json: todo514, after todo513, 2d
		5.4.1 Re-format the telemetry states signal: todo541, after todo43, 2d
		5.4.2 Format remotes signal: todo542, after todo541, 1d
		5.4.3 Send signal after a new config is added: todo543, after todo542, 2d
		5.5 Use the signal from button: todo55, after todo543, 1d
		5.6 Send signal to drive leds: todo56, after todo543, 1d
		5.7 Post data: todo57, after todo56, 2d
		As discussed please remove all the deamons not use within the UP scope: todo58, after todo57, 3d

```

## 2.2. Implement

```mermaid
gantt
	title 20230209-TaskList
	dateFormat  YYYY-MM-DD

  axisFormat %-m/%-d
	excludes weekends saturday,sunday, 2023-02-27, 2023-02-28

	section SPEC
		read 20230209-TaskList.pdf: crit, done, spec1, 2023-02-09, 1d
	section CODEBASE
		upgrade codebase and branch: crit, done, base1, after spec1, 3d
		download Artifacts-0.5.5 (without p7zip): crit, done, base2, 2023-02-13, 1d
		can't login the board: crit, done, base3, 2023-02-13, 2023-02-15
    download Artifacts-0.5.7: crit, done, base4, 2023-02-14, 2023-02-16
    upload the current commit history: crit, done, base5, 2023-03-01, 2023-03-02
    refactory get/update device (get the data from devicesV5.json): crit, done, base6, after base5, 2d
	section Current
		Have a look of the point 3, for the general flow: done, todo3, 2023-02-09, 1d
		4.3 (part1) Change the order using to the document and add for MFP (SPE-CommandsOrders.xlsx/UP_to_V5_Order): done, todo43, 2023-02-16, 1d
		4.3 (part2) Change the order using to the document and add for MFP (SPE-CommandsOrders.xlsx/UP_to_V5_Order): done, todo43a, 2023-02-23, 2d

		4.4 Format and store correctly the devicesV5.json and remotesV5.json: done, todo44, 2023-02-17, 2023-02-21
		4.5 Correctly format the json signal and add for MFP (See 5.4 Telemetry on this document): done, todo45, 2023-02-24, 1d
		4.7 Move you storage path to /etc/yokis/v5 and /etc/yokis/json: done, todo47, 2023-02-17, 2023-02-21
		5.1.3 Check that the command refresh correctly update the devicesV5.json: todo513, after base6, 2d
		5.1.4 Check taht the command update correctly update the devicesV5.json: todo514, after base6, 2d
		5.4.1 Re-format the telemetry states signal: done, todo541, 2023-02-23, 2023-03-02
		5.4.2 Format remotes signal: done, todo542, 2023-02-24, 2023-03-02
		5.4.3 Send signal after a new config is added: done, todo543, 2023-02-21, 2023-02-22
		5.5 Use the signal from button: done, todo55, 2023-02-17, 2023-02-21
		5.6 Send signal to drive leds: done, todo56, 2023-02-20, 1d
		5.7 Post data: done, todo57, 2023-02-21, 2023-02-24
		As discussed please remove all the deamons not use within the UP scope: done, todo58, 2023-02-13, 2023-02-17

```
