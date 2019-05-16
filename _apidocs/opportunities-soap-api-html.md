### getNoticeData

<details>
    <summary>Request Sample</summary>
<textarea>
``` 
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:sam="https://www.sam.gov/">
   <soapenv:Header>
<AuthenticationData xsi:type="sam:AuthenticationData">
        <username xsi:type="xsd:string">system account user name</username>
        <password xsi:type="xsd:string">system account password</password>
        <emailid xsi:type="xsd:string"> Email of the contracting officer/specialist who can submit opportunities </emailid>
   </soapenv:Header>
   <soapenv:Body>
      <sam:getNoticeData soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <data xsi:type="sam:NoticeDataRequest">
            <notice_id xsi:type="xsd:string">b9b337da8b994afd878e962bfb2810fa</notice_id>
            <!--Optional:-->
            <get_changes xsi:type="xsd:boolean"></get_changes>
            <!--Optional:-->
            <get_changes_from_date xsi:type="xsd:date"></get_changes_from_date>
            <!--Optional:-->
            <get_file_data xsi:type="xsd:boolean"></get_file_data>
         </data>
      </sam:getNoticeData>
   </soapenv:Body>
</soapenv:Envelope>
```
</textarea>
</details>

<details>
    <summary>Response sample – success</summary>
<textarea>
Note: This service gets a list of all notices
  ``` 
  <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Header/>
    <SOAP-ENV:Body>
        <ns1:getNoticeDataResponse xmlns:ns1="https://www.sam.gov/">
            <return xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:NoticeData">
                <success xsi:type="xsd:boolean">true</success>
                <messages xsi:nil="true" xsi:type="ns1:ArrayOfstring"/>
                <notice xsi:type="ns1:NoticeData">
                    <notice_id xsi:type="xsd:string">b9b337da8b994afd878e962bfb2810fa</notice_id>
                    <notice_type xsi:type="xsd:string">PRESOL</notice_type>
                    <agency xsi:type="xsd:string">TRANSPORTATION, DEPARTMENT OF</agency>
                    <office xsi:type="xsd:string">FEDERAL MOTOR CARRIER SAFETY ADMINISTRATION</office>
                    <location xsi:type="xsd:string">FMCSA GRANTS MANAGEMENT OFFICE</location>
                    <date xsi:type="xsd:date">Sat Jan 04 00:00:00 GMT 6425</date>
                    <classcod xsi:type="xsd:string">13</classcod>
                    <naics xsi:type="xsd:string">11150</naics>
                    <subject xsi:type="xsd:string">title</subject>
                    <solnbr xsi:type="xsd:string">testDm14</solnbr>
                    <archdate xsi:type="xsd:date">2030-01-01</archdate>
                    <desc xsi:type="xsd:string">test</desc>
                    <link xsi:type="xsd:string"/>
                    <contact xsi:type="xsd:string">Veera</contact>
                    <recovery_act xsi:type="xsd:string">none</recovery_act>
                    <document_packages xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" SOAP-ENC:arrayType="ns1:DocumentPackageData[1]" xsi:type="ns1:ArrayOfDocumentPackageData">
                        <item xsi:type="ns1:DocumentPackageData">
                            <package_id xsi:type="xsd:string">509d5e96c88a435c89503a64369141c9</package_id>
                            <label xsi:type="xsd:string"/>
                            <type xsi:type="xsd:string"/>
                            <files SOAP-ENC:arrayType="ns1:DocumentFileData[4]" xsi:type="ns1:ArrayOfDocumentFileData">
                                <item xsi:type="ns1:DocumentFileData">
                                    <file_id xsi:type="xsd:string">f16a71fdf4874edb8c4ce80281e3b36b</file_id>
                                    <type xsi:type="xsd:string">link</type>
                                    <filename xsi:type="xsd:string"/>
                                    <link xsi:type="xsd:string">http://beta.sam.gov</link>
                                    <desc xsi:type="xsd:string">test beta sam link</desc>
                                    <size_limit_error xsi:type="xsd:string">0</size_limit_error>
                                </item>
                                <item xsi:type="ns1:DocumentFileData">
                                    <file_id xsi:type="xsd:string">011b61f9e9154ed3bbe3f7aa21b1c2c1</file_id>
                                    <type xsi:type="xsd:string">link</type>
                                    <filename xsi:type="xsd:string">TAY VOR Scope of Work 10-25-17.pdf</filename>
                                    <link xsi:type="xsd:string">https://faaco.faa.gov/index.cfm/attachment/download/84723</link>
                                    <desc xsi:type="xsd:string">test attachment pdf link</desc>
                                    <size_limit_error xsi:type="xsd:string">0</size_limit_error>
                                </item>
                                <item xsi:type="ns1:DocumentFileData">
                                    <file_id xsi:type="xsd:string">ccb450b711734dce848c44f840d22a7a</file_id>
                                    <type xsi:type="xsd:string">file</type>
                                    <filename xsi:type="xsd:string">test_document1.pdf</filename>
                                    <filedata xsi:type="xsd:string">SnVzdCBhIHNtYWxsIHRl</filedata>
                                    <desc xsi:type="xsd:string"/>
                                    <size_limit_error xsi:type="xsd:string">0</size_limit_error>
                                </item>
                                <item xsi:type="ns1:DocumentFileData">
                                    <file_id xsi:type="xsd:string">91624a57e1bd4f15967f5a2b42f49dc0</file_id>
                                    <type xsi:type="xsd:string">file</type>
                                    <filename xsi:type="xsd:string">test_document2.pdf</filename>
                                    <filedata xsi:type="xsd:string">SnVzdCBhIHNtYWxsIHRlc3Q2</filedata>
                                    <desc xsi:type="xsd:string"/>
                                    <size_limit_error xsi:type="xsd:string">0</size_limit_error>
                                </item>
                            </files>
                        </item>
                    </document_packages>
                </notice>
            </return>
        </ns1:getNoticeDataResponse>
    </SOAP-ENV:Body>
    </SOAP-ENV:Envelope>
    ```

</textarea>
</details>

<details>
    <summary>Response sample – error</summary>
<textarea>
   ```
   <SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
       <ns1:getNoticeDataResponse xmlns:ns1="https://www.sam.gov/">
           <return xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:NoticeData">
               <success xsi:type="xsd:boolean">false</success>
               <messages xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" SOAP-ENC:arrayType="xsd:string[1]" xsi:type="ns1:ArrayOfstring">
                   <item xsi:type="xsd:string">notice_id from getList is required.</item>
               </messages>
           </return>
       </ns1:getNoticeDataResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```

</textarea>
</details>

### submitSaleOfSurplus

<details>
    <summary>Request Sample</summary>
<textarea>
```
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:sam="https://www.sam.gov/" xmlns:soapenc="http://schemas.xmlsoap.org/soap/encoding/">
   <soapenv:Header>
      <AuthenticationData xsi:type="sam:AuthenticationData">
        <username xsi:type="xsd:string">system account user name</username>
        <password xsi:type="xsd:string">system account password</password>
        <emailid xsi:type="xsd:string"> Email of the contracting officer/specialist who can submit opportunities </emailid>
     </AuthenticationData>
   </soapenv:Header>
   <soapenv:Body>
      <sam:submitSaleOfSurplus soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <data xsi:type="sam:SaleOfSurplus">
            <officeid xsi:type="xsd:string">100525144</officeid>
            <date xsi:type="xsd:date"></date>
            <zip xsi:type="xsd:string"></zip>
            <classcod xsi:type="xsd:string">13</classcod>
            <naics xsi:type="xsd:string">111150</naics>
            <!--Optional:-->
            <offadd xsi:type="xsd:string"></offadd>
            <subject xsi:type="xsd:string">Test sales surplus</subject>
            <solnbr xsi:type="xsd:string">testsalesur3</solnbr>
            <!--Optional:-->
            <archdate xsi:type="xsd:date"></archdate>
            <contact xsi:type="xsd:string">Veera</contact>
            <desc xsi:type="xsd:string">test desc</desc>
            <!--Optional:-->
            <link xsi:type="sam:GovURL">
               <url xsi:type="xsd:string"> </url>
               <desc xsi:type="xsd:string"> </desc>
            </link>
            <!--Optional:-->
            <email xsi:type="sam:GovEmail">
               <address xsi:type="xsd:string">abc@a.com</address>
               <desc xsi:type="xsd:string">email desc test</desc>
            </email>
            <!--Optional:-->
            <links xsi:type="sam:ArrayOfDocumentLink" soapenc:arrayType="sam:DocumentLink[]"/>
            <!--Optional:-->
            <files xsi:type="sam:ArrayOfDocumentFile" soapenc:arrayType="sam:DocumentFile[]"/>
            <!--Optional:-->
            <recovery_act xsi:type="xsd:boolean"></recovery_act>
         </data>
      </sam:submitSaleOfSurplus>
   </soapenv:Body>
</soapenv:Envelope>
```

</textarea>
</details>

<details>
    <summary>Response Sample – Success</summary>
<textarea>
```
<SOAP-ENV: xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
       <ns1:SubmitSaleOfSurplusResponse xmlns:ns1="https://www.sam.gov/">
           <return xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:PostingResponse">
               <success xsi:type="xsd:boolean">true</success>
               <messages xsi:nil="true" xsi:type="ns1:ArrayOfstring"/>
           </return>
       </ns1:SubmitSaleOfSurplusResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
</textarea>
</details>

<details>
    <summary>Response Sample – Failure</summary>
<textarea>
```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
       <ns1:SubmitSaleOfSurplusResponse xmlns:ns1="https://www.sam.gov/">
           <return xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:PostingResponse">
               <success xsi:type="xsd:boolean">false</success>
               <messages xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" SOAP-ENC:arrayType="xsd:string[5]" xsi:type="ns1:ArrayOfstring">
                   <item xsi:type="xsd:string">Contracting office is required</item>
                   <item xsi:type="xsd:string">PSC code is required</item>
                   <item xsi:type="xsd:string">Description is required</item>
                   <item xsi:type="xsd:string">Primary Contact is required</item>
                   <item xsi:type="xsd:string">Notice Id is required</item>
               </messages>
           </return>
       </ns1:SubmitSaleOfSurplusResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
</textarea>
</details>

### getIVLList
<details>
    <summary>Response Sample</summary>
<textarea>
```
<soapenv:Envelope xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:soapenv="http://schemas.xmlsoap.org/soap/envelope/" xmlns:sam="https://www.sam.gov/">
   <soapenv:Header>
     <AuthenticationData xsi:type="sam:AuthenticationData">
        <username xsi:type="xsd:string">system account user name</username>
        <password xsi:type="xsd:string">system account password</password>
      	  <emailid xsi:type="xsd:string">Email of the contracting officer/specialist who can submit opportunities</emailid>
     		</AuthenticationData>
   </soapenv:Header>
   <soapenv:Body>
      <sam:getIVLList soapenv:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">
         <data xsi:type="sam:IVLListRequest">
            <solnbr xsi:type="xsd:string">TEST_IVL_1</solnbr>
            <ntype xsi:type="xsd:string">PRESOL</ntype>
         </data>
      </sam:getIVLList>
   </soapenv:Body>
</soapenv:Envelope>
```
</textarea>
</details>

<details>
    <summary>Response Sample - Success</summary>
<textarea>
```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
    <SOAP-ENV:Header/>
    <SOAP-ENV:Body>
        <ns1:getIVLListResponse xmlns:ns1="https://www.sam.gov/">
            <return xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:IVLListResponse">
                <success xsi:type="xsd:boolean">true</success>
                <messages xsi:nil="true" xsi:type="ns1:ArrayOfstring"/>
                <data xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" SOAP-ENC:arrayType="ns1:IVL[1]" xsi:type="ns1:ArrayOfIVL">
                    <item xsi:type="ns1:IVL">
                        <lname xsi:type="xsd:string">SANGHANI</lname>
                        <fname xsi:type="xsd:string">MEHUL</fname>
                        <email xsi:type="xsd:string">mehul.sanghani@octoconsulting.com</email>
                        <phone xsi:type="xsd:string">5712750120</phone>
                        <contractor_name xsi:type="xsd:string">OCTO CONSULTING GROUP, INC.</contractor_name>
                        <dba_name xsi:type="xsd:string"/>
                        <duns xsi:type="xsd:string">800127859</duns>
                        <cage_code xsi:type="xsd:string">4RSC0</cage_code>
                        <address xsi:type="xsd:string">10780 PARKRIDGE BOULEVARD 4TH FLOOR RESTON VIRGINIA 20191 UNITED STATES</address>
                        <bus_types xsi:type="xsd:string"/>
                        <naics_codes xsi:type="xsd:string">511210,517110,517210,517911,518210,519130,541330,541511,541512,541513,541519,541611,541612,541613,541614,541618,541690,541712,541990</naics_codes>
                    </item>
                </data>
            </return>
        </ns1:getIVLListResponse>
    </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
</textarea>
</details>

<details>
    <summary>Response Sample - Failure</summary>
<textarea>
```
<SOAP-ENV:Envelope xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/">
   <SOAP-ENV:Header/>
   <SOAP-ENV:Body>
       <ns1:getIVLListResponse xmlns:ns1="https://www.sam.gov/">
           <return xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:type="ns1:IVLListResponse">
               <success xsi:type="xsd:boolean">false</success>
               <messages xmlns:SOAP-ENC="http://schemas.xmlsoap.org/soap/encoding/" SOAP-ENC:arrayType="xsd:string[1]" xsi:type="ns1:ArrayOfstring">
                   <item xsi:type="xsd:string">Multiple Notices found. Please input more details</item>
               </messages>
           </return>
       </ns1:getIVLListResponse>
   </SOAP-ENV:Body>
</SOAP-ENV:Envelope>
```
</textarea>
</details>

