<!DOCTYPE html>
<html class="no-js" lang="en">
  <head>
    <meta http-equiv="content-type" content="text/html; charset=UTF-8">
    <meta charset="utf-8">
    <meta http-equiv="x-ua-compatible" content="ie=edge">
    <meta name="description" content="">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <link rel="canonical" href="http://html5-templates.com/">
    <link rel="apple-touch-icon" href="apple-touch-icon.png">
    <!-- Place favicon.ico in the root directory -->
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <!--[if lt IE 8]>
            <p class="browserupgrade">You are using an <strong>outdated</strong> browser. Please <a href="https://browsehappy.com/">upgrade your browser</a> to improve your experience.</p>
        <![endif]-->
    <div class="wrapAll clearfix">
      <div class="mainsection"><br>
        <div class="article">
          <h1><font style="font-size: 20pt" size="5">Vaisala RS-41 SGP
              Modification.</font> </h1>
          <p class="siteSub">
          </p>
          <div class="articleRight">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; <img
              src="img/rs1.png" alt="rs41" width="79" height="270">&nbsp;
          </div>
          <br>
          <p style="user-select: auto !important; margin: 0px 0px 20px;
            padding: 0px; border: 0px; outline: 0px; font-size: 15px;
            vertical-align: baseline; background: 0px 0px rgb(255, 255,
            255); color: rgb(68, 68, 68); font-family: &quot;Helvetica
            Neue&quot;, sans-serif; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 300; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">Radiosondes are
            light weight sensor packages that are attached to weather
            balloons. <br>
            They transmit live RF weather telemetry down to earth as
            they rise. <br>
            One related hobby that a few people enjoy is radiosonde
            chasing, which is tracking and collecting radiosondes once
            they have fallen back to the earth. <br>
            Some people collect them as trophies, and others like to
            repurpose them.</p>
          <p style="user-select: auto !important; margin: 0px 0px 20px;
            padding: 0px; border: 0px; outline: 0px; font-size: 15px;
            vertical-align: baseline; background: 0px 0px rgb(255, 255,
            255); color: rgb(68, 68, 68); font-family: &quot;Helvetica
            Neue&quot;, sans-serif; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 300; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">Another way to
            repurpose radiosondes is to reprogram the commonly used
            Vaisala RS-41 radiosondes into being able to transmit radio
            APRS, 4FSK, RTTY or CW mode signals in the ISM or HAM bands.
            <br>
            The initial modified firmware was first performed by SQ5RWU,
            and then OM3BC who managed to create firmware able to
            configure settings thru the serial connection off the
            radiosonde.<br>
            Darkside did also modified firmware and added a very
            promising demodulation mode 4FSK, which not only decrease
            the package size but also has better coverage. <br>
            This firmware could be useful for anybody requiring a cheap
            transmitter for their own high altitude balloon experiments.<br>
          </p>
          <p style="user-select: auto !important; margin: 0px 0px 20px;
            padding: 0px; border: 0px; outline: 0px; font-size: 15px;
            vertical-align: baseline; background: 0px 0px rgb(255, 255,
            255); color: rgb(68, 68, 68); font-family: &quot;Helvetica
            Neue&quot;, sans-serif; font-style: normal;
            font-variant-ligatures: normal; font-variant-caps: normal;
            font-weight: 300; letter-spacing: normal; orphans: 2;
            text-align: start; text-indent: 0px; text-transform: none;
            white-space: normal; widows: 2; word-spacing: 0px;
            -webkit-text-stroke-width: 0px; text-decoration-style:
            initial; text-decoration-color: initial;">Also it is
            possible to enter the service menu of the Vaisala RS-41
            Radiosonde to learn more about its operation.<br>
          </p>
          <br>
          <div class="contentsPanel">
            <div class="contentsHeader">Contents:</div>
            <br>
            <ul>
                  <li><span>1.1&nbsp; <a href="#Hardware_Details_">Hardware
                        Details</a></span> </li>
                  <li><span>1.2&nbsp; <a href="#Needed_Stuff_">Needed
                        stuff</a>&nbsp;</span> </li>
                  <li><span>1.3&nbsp; <a href="#RS-41_Connector_">RS-41
                        Connector</a><br>
                    </span></li>
                  <li><span>1.4&nbsp; </span><a
                      href="#ST-Link_STM32_Connection_">ST-LINK STM32
                      Connection</a></li>
                  <li>1.5&nbsp; <a
                      href="#Orginal_Firmware_and_Terminal_Connection">Orginal
                      Firmware and Service Menu </a><br>
                  </li>
                  <li><span>1.6&nbsp; </span><a href="#Firmware_">Modified
                      Firmware</a> </li>
                  <li><span>1.7&nbsp; <a href="#Program_and_Flashing_">Program
                        and Flashing</a></span></li>
                  <li><span>1.8&nbsp; <a href="#Horus-Decoder_">Horus-Decoder</a><br>
                    </span></li>
                  <li><span>1.9&nbsp; </span><a href="#OM3BC_Firmware_">OM3BC
                      Firmware</a><a href="#Zilog_DFM_Decoder_Scripts_"><br>
                    </a></li>
                </ul>
              </li>
            </ul>
          </div>
          <h2><a name="Hardware_Details_"></a>Hardware Details<br>
          </h2>
          <br>
          The radiosonde RS41-SG was introduced by Vaisala in 2013. <br>
          On <a
href="https://www.vaisala.com/en/products/instruments-sensors-and-other-measurement-devices/soundings-products/rs41"
            target="_blank">Vaisala's website</a> it is possible to find
          very detailed specifications of the RS41-SG.<br>
          <br>
          <p style="margin-bottom: 0cm">LED Lights operation.</p>
          <p style="margin-bottom: 0cm">Red LED:<br>
            1 - Temperature or humidity sensor broken.<br>
            2 - Low battery.<br>
            3 - Battery should be empty.<br>
            4 - Expected interface, but there is none.<br>
            <br>
            Flashing Green LED:<br>
          </p>
          <p style="margin-bottom: 0cm">Insufficient data for GPS
            positions.<br>
            <br>
            After switching on the RS41, the LED will flashes four
            times.</p>
          <p style="margin-bottom: 0cm">Flashing Green LED:<br>
            1 - Turns red when something is wrong.<br>
            2 - Enable transmitter.<br>
            <br>
            When the Radiosonde is flying over 100 seconds,</p>
          <p style="margin-bottom: 0cm">1 - The LED goes out.<br>
            2 - And the transmitter operates at full power.</p>
          <br>
          PE2BZ - The point inside the red "rectangle" represents a source of power connection from 1 single 1.5 V battery, outside the switch.
          Operation goes up to 0.85 volts.</p>
          <br>
          <img src="img/RS41_pwr_conn.jpg" alt="" width="385" height="354"><br>
          <br>
          <a href="https://github.com/bazjo/RS41_Hardware"
            target="_blank">RS-41 Details Thanks to Bazjo</a><br>
          <h2><a name="Needed_Stuff_"></a>Needed Stuff<br>
          </h2>
          <br>
          USB-TTL converter.<br>
          Some wires and connectors.<br>
          Soldering tools.<br>
          ST-LINK STM32.<br>
          &nbsp;<br>
          <h2><a name="RS-41_Connector_"></a>RS-41 Connector<br>
          </h2>
          <br>
          <img src="img/RS41pinout2.jpg" alt="" width="385" height="354"><br>
          <br>
          <p style="margin-bottom: 0cm">1 - GND</p>
          <p style="margin-bottom: 0cm">2 - Uart3 Rx</p>
          <p style="margin-bottom: 0cm">3 - Uart3 Tx</p>
          <p style="margin-bottom: 0cm">4 - PB1 * (10k + cap + 10k)</p>
          <p style="margin-bottom: 0cm">5 - Vcc (Boost out) 5.0V</p>
          <p style="margin-bottom: 0cm">6&nbsp; VBAT 3.3V</p>
          <p style="margin-bottom: 0cm">7 - RST</p>
          <p style="margin-bottom: 0cm">8 - SWCLK</p>
          <p style="margin-bottom: 0cm">9 - SWDIO = SWID</p>
          <p style="margin-bottom: 0cm">10- GND</p>
          <br>
          <h2><a name="ST-Link_STM32_Connection_"></a>ST-Link STM32
            Connection<br>
          </h2>
          <p> <br>
            Download ST-LINK STM32 Software <a
              href="http://www.st.com/en/development-tools/stsw-link004.html"
              target="_blank">http://www.st.com/en/development-tools/stsw-link004.html</a><br>
          </p>
          <p style="margin-bottom: 0cm"><br>
          </p>
          <img src="img/ST-Link-V2-STM8-STM32.jpg" alt="stm" width="220"
            height="220"><br>
          Connect ST-LINK STM32:<br>
          <br>
          <p style="margin-bottom: 0cm">RS41 ----- ST-LINK</p>
          <p style="margin-bottom: 0cm">===================</p>
          <p style="margin-bottom: 0cm">Pin 1 ----- GND</p>
          <p style="margin-bottom: 0cm">Pin 8 ----- SWCLK</p>
          <p style="margin-bottom: 0cm">Pin 9 ----- SWDIO = SWID<br>
            <br>
          </p>
          <p style="margin-bottom: 0cm"><img src="img/conn.jpg" alt=""
              width="215" height="258"><br>
            <br>
          </p>
          <img src="img/ST-LINK.jpg" alt="" width="436" height="326"><br>
          <br>
          <h2><a name="Orginal_Firmware_and_Terminal_Connection"></a>Orginal
            Firmware and Service Menu </h2>
          <p style="margin-bottom: 0cm"><br>
          </p>
          For a terminal connection the following data pins are
          connected to the USB TTL Serial Converter in order to enter
          the service menu:<br>
          <br>
          <img src="img/sku_224704_1_small.jpg" alt="" width="140"
            height="140"><br>
          <br>
          <p style="margin-bottom: 0cm">Pin 1 ----- GND</p>
          <p style="margin-bottom: 0cm">Pin 2 ----- TxD</p>
          <p style="margin-bottom: 0cm">Pin 3 ----- RxD<br>
          </p>
          <p style="margin-bottom: 0cm"> Pin 4 ----- 3.3V<br>
            Or:<br>
          </p>
          Pin 5 ----- 3.3V<br>
          <img src="img/RS41pinout.jpg" alt="" width="346" height="490"><br>
          <br>
          <p>Build together -&gt;<br>
          </p>
          <img src="img/Terminal_connection.jpg" alt="" width="358"
            height="477"><br>
          <br>
          Connect a terminal (9k6 8N1) to the XDATA UART port. <br>
          <p style="margin-bottom: 0cm">Select COM Port (most probaly <a
href="http://www.prolific.com.tw/US/ShowProduct.aspx?p_id=225&amp;pcid=41"
              target="_blank">Prolific driver</a> is needed on Windows)
            .</p>
          <p style="margin-bottom: 0cm">Start (hyper)terminal like Putty
            and connect to serial COM Port and use 9600 Baud.</p>
          <br>
          <p>Power on RS-41, Welcome message should appear with
            information about software version, serial number, etc: </p>
          <p>Vaisala RS41 Radiosonde SW
            V2.02.14&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
            Copyright (c) Vaisala Oyj 2016. All rights
            reserved.&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
            Serial number: P1234567
            &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
            Pressure module serial number: Px SW
            V2.01&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
            Transmitter frequency: 403.90
            MHz&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
            Transmitter power:
            3/7&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
            Enabled TX&nbsp; <br>
          </p>
          <br>
          Now enter the following five characters and press Enter :<br>
          <p style="margin-bottom: 0cm">STwsv<br>
            <br>
            Press ENTER again and you should see a service menu.<br>
            Where you can change the TX power, frequency and more
            options.</p>
          <br>
          (S)ensors&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          Fre(q)uencies&nbsp; (P)arameters&nbsp;&nbsp;&nbsp;
          (A)lfa&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          TX p(o)wer<br>
          TX (f)requency&nbsp;&nbsp;&nbsp; T(X)
          state&nbsp;&nbsp;&nbsp;&nbsp; (T)X registers&nbsp; TX
          contin(u)ous&nbsp; TX ran(d)om<br>
          TX (c)arrier&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (B)aud
          rate&nbsp;&nbsp;&nbsp; Ser(i)al no&nbsp;&nbsp;&nbsp;&nbsp;
          (R)ed LED info&nbsp;&nbsp; (N)o menu<br>
          (K)eep test mode&nbsp; S(W) version&nbsp;&nbsp;
          (M)easurements&nbsp; (L)aunch/Drop&nbsp;&nbsp;&nbsp; (E)xit<br>
          &gt;Enabled TX<br>
          &nbsp;<br>
          A few examples:<br>
          <br>
          X Transmission of the data is stopped.<br>
          o Change power level 0 - 7.<br>
          f&nbsp; Change Frequency.<br>
          i&nbsp; Change Serial Number<br>
          K Keep test mode, with this setting you do not have to re
          enter the pw again in order to show the service menu.<br>
          M Measurements show the following menu:<br>
          <br>
          (S)ensors&nbsp;&nbsp;&nbsp;&nbsp; Fre(q)uencies&nbsp; S(W)
          reset&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; (D)efault
          params&nbsp; (U)se sensor<br>
          (R)eg offset&nbsp; Reg (c)heck&nbsp;&nbsp;&nbsp; (T)
          self-check&nbsp;&nbsp; St(o)p sequence&nbsp;&nbsp; (H)eat ref<br>
          (G)PS&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          (N)MEA&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
          D(I)rect GPS mode (E)xit<br>
          &nbsp;<br>
          D Direct GPS mode, with option the RS-41 can be used as a GPS
          mouse sending True NMEA bidirectional data via UART, you can
          also send "N" then just NMEA is output.<br>
          <br>
          Unfortunately, the settings are not retained after a power
          cycle.<br>
          <br>
          The (T)X Registers menu option allows reading and writing of
          arbitrary register values. <br>
          However, these changes are not persistent, and get overwritten
          on startup, and whenever the transmitter is disabled and
          re-enabled.<br>
          The (T)X register menu is used by entering:<br>
          Txx\r&nbsp;&nbsp; (where xx is the register value in hex)<br>
          You get a prompt as follows:<br>
          &nbsp;&gt;T<br>
          Register number (00-7F) &gt;77<br>
          Register value E3 &gt;<br>
          At this point you can either send a \r to exit back to the
          main menu, or you can enter a value in hex + \r which will be
          written to that register.<br>
          Example RS41 onto the 70cm band (434.650 MHz) by programming
          the following values:<br>
          <br>
          0x75: 61<br>
          0x76: 10<br>
          0x77: D3<br>
          <br>
          A very handy online Calculator for more Frequencies is <a
href="https://www.makemehack.com/2020/12/how-to-change-the-tx-frequency-of-the-vaisala-rs41-radiosonde.html"
            target="_blank">overhere</a>.<br>
          <br>
          P (parameters):<br>
          <br>
          Data ID is a hexadecimal number.<br>
          The value does not seem to have any meaning other than being
          used as a selector.<br>
          Values ​​are strings or decimal numbers.<br>
          <br>
          ID card Value Changeable Note:
          <p style="margin-bottom: 0cm">10 5 *<br>
            20 14 *<br>
            30 0 *<br>
            40 0 *<br>
            45 S0341201 * Serial number<br>
            50 RS41-SG * RS41 model<br>
            60 20215 --- Firmware Version (V2.02.15)<br>
            70 9089 *<br>
            80 4 ---<br>
            90 5 ---<br>
            A0<br>
            B0<br>
            C0<br>
            D0 600 * Height [m] above the launch site that the RS41 must
            climb to before entering flight mode.<br>
            E0 18 * Low battery voltage threshold [100 mV] below which
            the probe will turn off (if the condition persists for some
            time). 18 = 1.8V<br>
            100180<br>
            110 60<br>
            120 1700<br>
            130 20<br>
            140135<br>
            150 50<br>
            160 1<br>
            170 RSM412 PCB type<br>
            180 R4550425 PCB serial<br>
            190 0000000000<br>
            1A0<br>
            1A8<br>
            1B0<br>
            1B8<br>
            1C0<br>
            1C8<br>
            1D0<br>
            1D5<br>
            1D8<br>
            1E0<br>
            200 29 --- Current battery voltage [100 mV]. 29 = 2.9 V.<br>
            210 0 ---<br>
            220 41 --- Current CPU temperature [° C]<br>
            230 48 --- Current radio temperature (Si4032) [° C]<br>
            240 1 ---<br>
            250 42 --- Current temperature reference range [° C]<br>
            255<br>
            260</p>
          <h2><a name="Firmware_"></a>Modified Firmware<br>
          </h2>
          <p style="margin-bottom: 0cm"><br>
            There are a few different firmware's each with their
            advantages.<br>
          </p>
          <br>
          1: 70cm Band, GPS and telemetry data in RTTY, APRS and CW on
          seperately defineable TX frequencies.<br>
          <a href="https://github.com/df8oe/RS41HUP" target="_blank">https://github.com/df8oe/RS41HUP</a><br>
          <br>
          <p style="margin-bottom: 0cm">2: 70cm Band, GPS and telemetry
            data in CW, RS41-FOX - RS41 Amateur Radio Direction Finding
            (Foxhunting) Beacon<br>
            This codebase turns a Vaisala RS41 into a 70cm 'radio fox',
            suitable for use in amateur radio direction finding
            contests. <br>
            <a href="https://github.com/darksidelemm/RS41FOX"
              target="_blank">https://github.com/darksidelemm/RS41FOX</a><br>
          </p>
          <p style="margin-bottom: 0cm">Features:</p>
          <p style="margin-bottom: 0cm"> Morse Ident containing callsign
            &amp; current battery voltage.<br>
            Long CW beacon (user-defined length and number of repeats)<br>
            Low-Voltage Cutout, to avoid destroying rechargable
            batteries.<br>
            Beacon GPS position when battery is below a user-defined
            threshold.<br>
            <br>
          </p>
          <p style="margin-bottom: 0cm">3: 70cm Band, GPS and telemetry
            data in 4FSK and RTTY.<br>
            <a href="https://www.rowetel.com/?p=5906" target="_blank">Information
              on the 4FSK mode's performance.</a><br>
          </p>
          <p style="margin-bottom: 0cm">Recommend for short and long HAB
            floater flights.<br>
          </p>
          <a href="https://github.com/darksidelemm/RS41FOX"
            target="_blank"></a><br>
          <p style="margin-bottom: 0cm"> Features:</p>
          <p style="margin-bottom: 0cm">Powersave modes for Radio:<br>
            Then the transmitter will turn off between transmissions,
            saves about 50mA of power consumption.<br>
          </p>
          <p style="margin-bottom: 0cm">GPS in PowerSave Mode,
            Transmitting @ 13 dBm = ~120 mA, not Transmitting = 30-50mA,
            depending on GPS state.<br>
          </p>
          <p style="margin-bottom: 0cm">Deep Sleep Mode intended for
            long duration flights only!<br>
            Power consumption in sleep mode = 32mA @ 3V<br>
            <br>
            In this mode, the GPS is turned into a sleep mode in between
            transmissions.<br>
            During this sleep period, we sent one 'pip' every few
            seconds.<br>
            At the end of the sleep period, the GPS is powered back up,
            and we await the GPS to obtain a fix before transmitting our
            position. <br>
            While waiting for GPS lock, we send a 'double pip'.</p>
          <p style="margin-bottom: 0cm">Tracking sonde position from
            habhub.<br>
            <br>
            <a href="https://github.com/darksidelemm/RS41HUP"
              target="_blank">https://github.com/darksidelemm/RS41HUP</a></p>
          <p style="margin-bottom: 0cm"><br>
          </p>
          <p style="margin-bottom: 0cm">Settings and Config (edit in
            config.h) for this software must be written before flashing.<br>
            <br>
          </p>
          <p>Grab the latest GNU ARM Embedded toolchain from here: <a
href="https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads"
              target="_blank">https://developer.arm.com/open-source/gnu-toolchain/gnu-rm/downloads</a><br>
            Extract the tarball to ~/opt/</p>
          <p>Within the RS41HUP directory:<br>
            Edit CMakeLists.txt and set the correct path to the un-tar'd
            directory.<br>
            cmake .<br>
            make<br>
            <br>
          </p>
          <img src="img/make.jpg" alt="" width="372" height="273"><br>
          <p><br>
          </p>
          <p><b>Note:</b><br>
          </p>
          <p>For your own flights, you will need to request a payload
            ID.</p>
          <p>Payload IDs can be requested by either raising an Issue, or
            a Pull Request on
            https://github.com/projecthorus/horusdemodlib/</p>
          Change the payload ID in config.h<br>
          #define BINARY_PAYLOAD_ID 0 // Payload ID for use in Binary
          packets <br>
          <br>
          Use the newly created bin or hex file to flash the RS-41.<br>
          <br>
          <h2><a name="Program_and_Flashing_"></a>Program and
            Flashing&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
            <br>
          </h2>
          <br>
          <img src="img/ST-LINK2.jpg" alt="" width="501" height="375"><br>
          <br>
          Connect RS-41 and power on.<br>
          <br>
          Open ST-Link Utility:<br>
          <p style="margin-bottom: 0cm"><br>
          </p>
          <img src="img/ST-Link_util.jpg" alt="st link" width="410"
            height="300"><br>
          <br>
          <p style="margin-bottom: 0cm">Load bin or hex file.<br>
            <br>
          </p>
          <img src="img/ST-Link_util2.jpg" alt="" width="415"
            height="301">
          <p style="margin-bottom: 0cm"><br>
          </p>
          <p style="margin-bottom: 0cm">In target menu select Connect.<br>
            <br>
          </p>
          <img src="img/ST-Link_util3.jpg" alt="" width="357"
            height="143">
          <p style="margin-bottom: 0cm"><br>
          </p>
          <p style="margin-bottom: 0cm"> </p>
          <p style="margin-bottom: 0cm">This message can happen:</p>
          <p>Can not read memory!</p>
          <p>Read out protection is activated</p>
          <p>Disable Read Out Protection and retry.</p>
          <p>In the target menu/option bytes/ disable bytes read out
            protection.<br>
            <br>
          </p>
          <img src="img/ST-Link_util4.jpg" alt="" width="484"
            height="395"><br>
          <br>
          Target menu select Program and wait for flash to finish and
          disconnect.<br>
          Disconnect RS-41 and ST-LINK STM32.<br>
          <br>
          <h2><a name="Horus-Decoder_"></a>Horus-Decoder<br>
          </h2>
          <br>
          Telemetry demodulator for the following modems in use by
          Project Horus and <a
            href="https://github.com/darksidelemm/RS41HUP"
            target="_blank">RS-41 4FSK Modified Firmware</a><br>
          <br>
          Horus Binary Modes (4FSK)<br>
          v1 - Legacy 22 byte mode, Golay(23,12) FEC<br>
          v2 - 16/32-byte modes, LDPC FEC (Under development)<br>
          RTTY (7N1, 7N2 and 8N2, standard UKHAS sentences with CRC16
          only)<br>
          <br>
          <a href="https://rfhead.net/horus/horusgui/" target="_blank">Windows
            builds overhere</a><br>
          <a href="https://github.com/projecthorus/horusbinary"
            target="_parent">Linux decoder for the 4FSK mode is
            available overhere</a><br>
          <br>
          <img src="img/gqrx.jpg" alt="" width="662" height="425"><br>
          <br>
          Flash RS-41 with <a
            href="https://github.com/darksidelemm/RS41HUP"
            target="_blank">4FSK Modified Firmware</a><br>
          Tune in with any SDR Application (<a
            href="https://github.com/projecthorus/horusdemodlib"
            target="_parent">or the Horus rtl_fm scripts</a>) on the
          frequency specified in config.h in USB Mode.<br>
          <br>
          Start Horus-gui decoder:<br>
          <br>
          <img src="img/horus-gui.jpg" alt="" width="678" height="392"><br>
          <br>
          Select audio device (in this example YDP thru GQRX is used).<br>
          Mode RTTY of 4FSK, check mark for data feed to <a
            href="https://tracker.habhub.org/" target="_blank">habhub
            upload.</a><br>
          <br>
          Output is also possible with UDP thru <a
            href="https://github.com/projecthorus/chasemapper/"
            target="_blank">Chasemapper.</a><br>
          <p> </p>
          <h2><a name="OM3BC_Firmware_"></a>OM3BC Firmware<br>
          </h2>
          <br>
          70cm Band, GPS and telemetry data in RTTY, APRS and CW on
          seperately defineable TX frequencies,<br>
          configurable settings thru terminal serial connection from the
          radiosonde. <br>
          <a href="http://www.om3bc.com/docs/rs41/rtty.hex"
            target="_blank">Hex file for flashing from om3bc.com</a><br>
          Recommend for playing with the Radiosonde but not for real
          flight's GPS outage occur for shorts periods during flight.<br>
          APRS callsign bugs.<br>
          <br>
          <p style="margin-bottom: 0cm">Start (hyper)terminal like Putty
            and connect to serial COM Port and use 9600 Baud.</p>
          Power on RS-41, Welcome message should appear:<br>
          <br>
          <img src="img/welcome.jpg" alt="ter" width="367" height="229">
          <p style="orphans: 2; widows: 2"><span style="font-variant:
              normal"><font color="#000000"><font face="Liberation
                  Serif, serif"><font style="font-size: 12pt" size="3"><span
                      style="letter-spacing: normal"><span
                        style="font-style: normal"><span
                          style="font-weight: normal">$$$$$$ STM32 RTTY
                          &amp; APRS tracker by OM3BC ...<br>
                          cmd&gt;</span></span></span></font></font></font></span><span
              style="font-variant: normal"><font color="#000000"><font
                  face="Times New Roman"><font style="font-size: 14pt"
                    size="4"><span style="letter-spacing: normal"><span
                        style="font-style: normal"><span
                          style="font-weight: normal"><br>
                          <br>
                        </span></span></span></font></font></font></span><span
              style="font-variant: normal"><font color="#000000"><font
                  face="Liberation Serif, serif"><font style="font-size:
                    12pt" size="3"><span style="letter-spacing: normal"><span
                        style="font-style: normal"><span
                          style="font-weight: normal">Allowed commands
                          (not case sensitive):<br>
                          <br>
                          BUTTON ON / OFF - use button to turn off /
                          this parameter specifies whether the push
                          button can be used to turn off the radiosonde
                          or not.<br>
                          LEDs on / off - use LEDs / you can save energy
                          when you do not use LEDs. After switching on,
                          the LEDs always work, but when set to OFF,
                          they automatically turn off after 10 minutes
                          of operation.<br>
                          POWER n - rf power n = 1 to 7 (7 is max.) /
                          output power setting 0 = smallest, 7 = maximum
                          power (approx. 40 mW).<br>
                          APRSFRQ n - n = aprs frequency in kHz / APRS
                          frequency (recommended frequency is 432,500
                          MHz)<br>
                          RTTYFRQ n - n = rtty frequency in kHz / RTTY
                          frequency. This frequency is also valid for CW
                          identification.<br>
                          APRSCALL string - aprs callsign (up to 6
                          characters)<br>
                          RTTYCALL string - rtty callsign (up to 15
                          characters)<br>
                          CWIDMESS string - cw message (up to 25
                          characters)<br>
                          RTTY on / off - send rtty message<br>
                          HOLDOFF n - n = time between two rtty messages
                          in seconds<br>
                          BAUD n - n = rtty baudrate<br>
                          DBITS n - n = rtty databits (7 or 8)<br>
                          SBITS n - n = rtty stop bits (1 or 2)<br>
                          SHIFT n - n = 1,2,3,4 1 = 270, 2 = 540, 3 =
                          810, 4 = 1080 Hz<br>
                          TEMP on / off - send temperature in rtty
                          messages / (The value is the temperature of
                          the radio chip, not the environment.)<br>
                          ALT on / off - send altitude in rtty &amp;
                          aprs messages<br>
                          SPEED on / off - send speed in rtty messages<br>
                          COURSE ON / OFF - send course in rtty messages<br>
                          UBAT on / off - send battery voltage in rtty
                          messages<br>
                          USYS on / off - send system voltage in rtty
                          messages / This is a constant value for
                          testing only.<br>
                          SAT on / off - the number of GPS satellites
                          heard in rtty messages<br>
                          APRS on / off - send aprs messages<br>
                          SPEEDCOURSE on / off - send speed and course
                          in aprs messages<br>
                          SYMBOL string - symbol from aprs symbol table
                          (2 characters) / two characters that determine
                          how the radiosonde appears on the www.aprs.fi
                          website. <br>
                          SSID n - aprs ssid n = 1 to 15 / </span></span></span></font></font></font></span><span
              style="font-variant: normal"><font color="#000000"><font
                  face="Liberation Serif, serif"><font style="font-size:
                    12pt" size="3"><span style="letter-spacing: normal"><span
                        style="font-style: normal"><span
                          style="font-weight: normal">t</span></span></span></font></font></font></span><span
              style="font-variant: normal"><font color="#000000"><font
                  face="Liberation Serif, serif"><font style="font-size:
                    12pt" size="3"><span style="letter-spacing: normal"><span
                        style="font-style: normal"><span
                          style="font-weight: normal">he caller ID of
                          the APRS. <br>
                          TXD n - Tx delay n = 10 to 500<br>
                          MICE on/off - send coded aprs messages in
                          mic-e format<br>
                          TELEMETRY on/off - send telemetry data in aprs
                          messages<br>
                          APRS_EVERY n - time between aprs messages is n
                          x holdoff / APRS packages are not required to
                          be given too often. This parameter specifies
                          the time between the two packets.<br>
                          TAIL_EVERY n - time between tail text is n x
                          aprs time / frequency of transmission of the
                          attached information text (comment field).<br>
                          TTEXT string - tail text (up to 100
                          characters) / attached information text
                          (comment).<br>
                          CWID on/off - send cwid messages<br>
                          CWID_EVERY n - time between cw messages is n x
                          holdoff<br>
                          CW_SPEED n n = the CW identification speed in
                          WPM.<br>
                          IGATE on/off - monitoring aprs message via
                          UART / after the parameter has been enabled,
                          the radiosonde sends a text through the serial
                          port that the iGate can link to.<br>
                          NMEA on/off - send MNEA GPGGA and GPRMC
                          messages via UART / If the parameter has been
                          enabled, the radiosonde sends standard NMEA
                          GPGGA and GPRMC text via the serial port.<br>
                          DISP - shows the set parameters.<br>
                          SERCOM n - speed of serial communication port
                          (n =&nbsp;300 to 115200)<br>
                          DEF - set parameters to default values.<br>
                          SAVE - save parameters to flash<br>
                          <br>
                          If you need help, you can use the HELP or the
                          ? command. </span></span></span></font></font></font></span><br>
            <br>
          </p>
          <img src="img/w7.jpg" alt="gqrx2" width="641" height="404"><br>
          <br>
          RS-41 Sending APRS Decode with Soundmodem.<br>
          <br>
          <img src="img/xub.jpg" alt="gqrx" width="643" height="405"><br>
          <br>
          RS-41 Sending RTTY Decode with FLdigi.<br>
          <br>
          <img src="img/ax25.jpg" alt="gps" width="642" height="386"><br>
          <br>
          APRS Position showing in APRSIS32.<br>
          <br>
          <img src="img/PE2BZ.jpg" alt="raam" width="640" height="437">
          <p style="orphans: 2; widows: 2">Connect it with Solar panels
            like PE2BZ did and launch it :)</p>
          <p> <br>
          </p>
          <p>Note:</p>
          <p><a href="https://airspy.com/download/" target="_blank">SDRSharp</a></p>
          <p><a href="http://gqrx.dk/" target="_blank">Gqrx</a></p>
          <p><a href="http://uz7.ho.ua/packetradio.htm" target="_blank">UZ7HO
              SoundModem</a></p>
          <p><a
href="https://drive.google.com/open?id=160_7nVCYmewZSPXMG9on-2Gah_uHO5KP"
              target="_blank">FLdigi Appimage</a></p>
          <p><a
              href="https://sourceforge.net/projects/fldigi/files/fldigi/"
              target="_blank">FLdigi Windows</a></p>
          <p>ST-LINK STM32 / USB-TTL Converter can be found on Ali/Ebay.</p>
        </div>
    </div>
  </body>
</html>
