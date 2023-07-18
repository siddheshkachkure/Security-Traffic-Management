without ipsec

refer copy for problem
vms : 2 windows 1 kali
all on nat mode

windows
192.168.100.156 Kali
192.168.100.157 WM1
192.168.100.158 WM2

machine windows 1
server manager -manage add rules feature
![Windows Server 2016 (1) - ftp service](https://github.com/shubnimkar/Alpha-one/assets/46809421/8f221cb7-8870-460f-aeb4-b98e87a3fb46)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_04_55](https://github.com/shubnimkar/Alpha-one/assets/46809421/8a970c1c-4682-44c6-8bb2-70beb392fee3)

# create user
![Capture](https://github.com/shubnimkar/Alpha-one/assets/46809421/d75a0718-6b89-457f-8a7f-eb9a0126e59c)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_08_42](https://github.com/shubnimkar/Alpha-one/assets/46809421/d276c935-3a48-442a-9cdf-200bdc2df18c)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_08_52](https://github.com/shubnimkar/Alpha-one/assets/46809421/4c0a265a-fb8b-4860-aeb0-822416741e28)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_09_26](https://github.com/shubnimkar/Alpha-one/assets/46809421/fab111f4-8c6e-49d1-aef1-828f6da62fd2)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_10_41](https://github.com/shubnimkar/Alpha-one/assets/46809421/638855b5-30bb-4907-8edc-8c7534388d0f)

# ftp site in IIS

![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_12_05](https://github.com/shubnimkar/Alpha-one/assets/46809421/484882ca-0648-4808-82b4-41b724068ee9)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_12_39](https://github.com/shubnimkar/Alpha-one/assets/46809421/cab7c9d5-ade4-43d4-a04b-eee62ad44e84)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_13_19](https://github.com/shubnimkar/Alpha-one/assets/46809421/c330d436-7cbe-49f8-892c-4b2f496cbaae)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_13_54](https://github.com/shubnimkar/Alpha-one/assets/46809421/10218b4b-1e9b-42b1-aaed-f07121b15906)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_14_00](https://github.com/shubnimkar/Alpha-one/assets/46809421/7000fded-0454-415d-973b-1569ea2a4f9b)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_15_39](https://github.com/shubnimkar/Alpha-one/assets/46809421/43846664-aca8-4a67-9e96-b66a6eaa5d6a)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_16_26](https://github.com/shubnimkar/Alpha-one/assets/46809421/e3713008-9ad1-40ce-b37f-ebcd44ce1c29)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_16_55](https://github.com/shubnimkar/Alpha-one/assets/46809421/d1dbe19c-f8a8-4903-b316-06044d43b975)



# create file
c:\inetpub\ftproot
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_19_09](https://github.com/shubnimkar/Alpha-one/assets/46809421/bb4359c1-dd55-4306-827c-7c317ca8362b)

now shutdown firewall
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_19_09](https://github.com/shubnimkar/Alpha-one/assets/46809421/208eb9b1-8bc4-4542-b2b1-19ad2125c3eb)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_19_18](https://github.com/shubnimkar/Alpha-one/assets/46809421/72d452f4-85eb-422c-a67e-856ca0465e60)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_19_29](https://github.com/shubnimkar/Alpha-one/assets/46809421/e9f1c3ef-90a6-4af4-b223-9055ca5d90d3)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_19_39](https://github.com/shubnimkar/Alpha-one/assets/46809421/a977bf97-6dfa-4799-8db7-36885b70fa9f)



now machine 2
cmd 
ftp wm1 ka ip
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 13_23_07](https://github.com/shubnimkar/Alpha-one/assets/46809421/05f583f7-8e5e-4b17-be5c-3381e285e635)

wireshark
![Kali - VMware Workstation 01-07-2023 14_34_40](https://github.com/shubnimkar/Alpha-one/assets/46809421/b48f53a8-f554-4bbe-856e-e77e667527ee)
![Kali - VMware Workstation 01-07-2023 14_40_32](https://github.com/shubnimkar/Alpha-one/assets/46809421/10df87c4-d7aa-4ea4-8fa8-5dc853eff213)

# with ipsec
# AH
wm1
![sec](https://github.com/shubnimkar/Alpha-one/assets/46809421/a4a5dec5-f6eb-4629-b190-a79b2a320865)
![Kali - VMware Workstation 01-07-2023 14_43_56](https://github.com/shubnimkar/Alpha-one/assets/46809421/1d4c23aa-fde9-4aa4-ab3f-d5d3d5bcfa8d)
![Kali - VMware Workstation 01-07-2023 14_44_42](https://github.com/shubnimkar/Alpha-one/assets/46809421/909ca8a0-1c26-4c1f-b728-567a78bf01c8)
![Kali - VMware Workstation 01-07-2023 14_44_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/067baba9-f234-40e2-b8bd-28d214ef4d5f)
![Kali - VMware Workstation 01-07-2023 14_45_20](https://github.com/shubnimkar/Alpha-one/assets/46809421/93058e0a-bc52-4913-984f-33167914ff51)
![Kali - VMware Workstation 01-07-2023 14_45_37](https://github.com/shubnimkar/Alpha-one/assets/46809421/835e3c68-14b7-4a37-b28b-5616909ffb7d)
![Kali - VMware Workstation 01-07-2023 14_45_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/85a77d33-2bcc-4e13-b89c-64ef92e0d122)
![Kali - VMware Workstation 01-07-2023 14_46_21](https://github.com/shubnimkar/Alpha-one/assets/46809421/9da9557f-fdbe-4102-9eb7-cad9fdfa61d8)
![Kali - VMware Workstation 01-07-2023 14_47_55](https://github.com/shubnimkar/Alpha-one/assets/46809421/122eacf2-9c97-47fa-b739-d3ac0b108620)
![Kali - VMware Workstation 01-07-2023 14_48_04](https://github.com/shubnimkar/Alpha-one/assets/46809421/715d7097-6cb1-4c39-8395-c7876bb1cabc)
![Kali - VMware Workstation 01-07-2023 14_50_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/fdbe62dc-6bac-4714-a299-85d1ba773a97)
![Kali - VMware Workstation 01-07-2023 14_51_50](https://github.com/shubnimkar/Alpha-one/assets/46809421/6e4e8cf5-c94b-44b7-b957-2f8d6f72d4a3)
![Kali - VMware Workstation 01-07-2023 14_54_21](https://github.com/shubnimkar/Alpha-one/assets/46809421/1455632c-6d75-4f64-ba07-8fd55368ad67)
![Kali - VMware Workstation 01-07-2023 14_54_40](https://github.com/shubnimkar/Alpha-one/assets/46809421/897da3f3-6ff0-4744-85e4-ebf0bdfdb1ea)
![Kali - VMware Workstation 01-07-2023 14_55_06](https://github.com/shubnimkar/Alpha-one/assets/46809421/1695c69c-cdab-4d27-8fe0-2048e195ef1b)
![Kali - VMware Workstation 01-07-2023 14_56_56](https://github.com/shubnimkar/Alpha-one/assets/46809421/f3ad66c0-d477-4758-b534-69294acd26f9)
![Kali - VMware Workstation 01-07-2023 14_57_15](https://github.com/shubnimkar/Alpha-one/assets/46809421/caf78c39-aee1-4c8e-8550-bebdfb00597b)
![Kali - VMware Workstation 01-07-2023 14_57_35](https://github.com/shubnimkar/Alpha-one/assets/46809421/7b7aefc2-b540-48c4-a44c-28e27218e4f1)
![Kali - VMware Workstation 01-07-2023 15_00_56](https://github.com/shubnimkar/Alpha-one/assets/46809421/2e0fbf0d-ca9c-446d-a4e4-ed8500b55a1b)
![Kali - VMware Workstation 01-07-2023 15_01_08](https://github.com/shubnimkar/Alpha-one/assets/46809421/030a57fc-d517-427b-aef8-8a1f9907fe62)
![Kali - VMware Workstation 01-07-2023 15_01_22](https://github.com/shubnimkar/Alpha-one/assets/46809421/cb135154-8b24-4b38-a932-d2a9b2975830)
![Kali - VMware Workstation 01-07-2023 15_01_55](https://github.com/shubnimkar/Alpha-one/assets/46809421/8799d395-42bc-475e-aa4e-2f0c7aeb3a3d)
![Kali - VMware Workstation 01-07-2023 15_03_12](https://github.com/shubnimkar/Alpha-one/assets/46809421/898cc350-797e-4fb3-a2ab-a918a11853ef)
![Kali - VMware Workstation 01-07-2023 15_04_09](https://github.com/shubnimkar/Alpha-one/assets/46809421/3a49e523-dfbe-43a7-9799-bcf5501281ff)
![Kali - VMware Workstation 01-07-2023 15_04_38](https://github.com/shubnimkar/Alpha-one/assets/46809421/d5d22467-bd61-4843-88c9-618f8719d145)
![Kali - VMware Workstation 01-07-2023 15_05_01](https://github.com/shubnimkar/Alpha-one/assets/46809421/7a3e39fc-52cd-451c-88d9-29486cdfc4df)
![Kali - VMware Workstation 01-07-2023 15_06_19](https://github.com/shubnimkar/Alpha-one/assets/46809421/2543810d-6a45-4aaf-b30c-629a524ba0cb)
![Kali - VMware Workstation 01-07-2023 15_06_26](https://github.com/shubnimkar/Alpha-one/assets/46809421/2bac5793-6682-44bb-8327-367e8ddacabb)
![Kali - VMware Workstation 01-07-2023 15_07_37](https://github.com/shubnimkar/Alpha-one/assets/46809421/2c396b29-298d-49e3-89eb-48872e8988de)

# on wm 2
![Kali - VMware Workstation 01-07-2023 15_09_51](https://github.com/shubnimkar/Alpha-one/assets/46809421/b4c3bb6a-3efc-4071-aeba-03a565748b4e)
![Kali - VMware Workstation 01-07-2023 15_11_32](https://github.com/shubnimkar/Alpha-one/assets/46809421/b3eaa5e2-10a2-4fde-baf2-080992886788)
![Kali - VMware Workstation 01-07-2023 15_13_08](https://github.com/shubnimkar/Alpha-one/assets/46809421/f10477fb-a864-4de3-b713-34a53b60e079)
![Kali - VMware Workstation 01-07-2023 15_13_23](https://github.com/shubnimkar/Alpha-one/assets/46809421/3e15fe66-1170-4ce2-b1c2-e8f0dba8ed08)
![Kali - VMware Workstation 01-07-2023 15_14_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/97787aa2-b0bf-43f3-a1f5-68b63f391249)
![Kali - VMware Workstation 01-07-2023 15_14_54](https://github.com/shubnimkar/Alpha-one/assets/46809421/a2c962e3-6f8a-473d-aa59-d40b569a5ed0)
![Kali - VMware Workstation 01-07-2023 15_15_11](https://github.com/shubnimkar/Alpha-one/assets/46809421/57aa02e8-a340-496f-9b32-56a2a34883dd)
![Kali - VMware Workstation 01-07-2023 15_15_33](https://github.com/shubnimkar/Alpha-one/assets/46809421/664ff610-4d8a-4fb3-af8f-0af6c0d118c2)
![Kali - VMware Workstation 01-07-2023 15_15_42](https://github.com/shubnimkar/Alpha-one/assets/46809421/db7c6714-90c9-4385-a953-4d733ff3dccf)
![Kali - VMware Workstation 01-07-2023 15_16_06](https://github.com/shubnimkar/Alpha-one/assets/46809421/bfe8142b-0f8e-438b-9f82-3fdcaa36a168)
![Kali - VMware Workstation 01-07-2023 15_16_36](https://github.com/shubnimkar/Alpha-one/assets/46809421/17f26d1e-d4f0-4028-935e-3369daf33489)
![Kali - VMware Workstation 01-07-2023 15_17_40](https://github.com/shubnimkar/Alpha-one/assets/46809421/fe127769-e6f4-4bb3-a11c-53d1e92b0b13)
![Kali - VMware Workstation 01-07-2023 15_17_55](https://github.com/shubnimkar/Alpha-one/assets/46809421/23976cfe-a985-480a-b555-da2dde07d5a5)
![Kali - VMware Workstation 01-07-2023 15_19_06](https://github.com/shubnimkar/Alpha-one/assets/46809421/7d5349f1-ed0c-460f-8b03-cbd649d74140)




# wm2
![Kali - VMware Workstation 01-07-2023 15_42_41](https://github.com/shubnimkar/Alpha-one/assets/46809421/8871d906-058e-48d4-92d3-4895ae7a8e47)
![Kali - VMware Workstation 01-07-2023 15_42_55](https://github.com/shubnimkar/Alpha-one/assets/46809421/ff09c817-d758-4ac1-801e-a7a508a39749)
![Kali - VMware Workstation 01-07-2023 15_43_07](https://github.com/shubnimkar/Alpha-one/assets/46809421/44db8599-851e-465e-94a0-58972ef191aa)
![Kali - VMware Workstation 01-07-2023 15_43_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/15375534-e146-4b44-9cbc-cc7aaf03b01b)
![Kali - VMware Workstation 01-07-2023 15_44_13](https://github.com/shubnimkar/Alpha-one/assets/46809421/ee34363a-af0e-4522-ad8f-565201a0c0b8)
![Kali - VMware Workstation 01-07-2023 15_44_39](https://github.com/shubnimkar/Alpha-one/assets/46809421/d84f7ba9-a365-47c6-b963-aaf1980efacf)

# wm1
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_45_53](https://github.com/shubnimkar/Alpha-one/assets/46809421/4151ee1e-68c2-4f57-936f-ac2672286652)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_46_54](https://github.com/shubnimkar/Alpha-one/assets/46809421/61dcb88e-5733-4565-a3cc-008ba1a2a2c3)

# on wm1 create website
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_55_40](https://github.com/shubnimkar/Alpha-one/assets/46809421/2a9c78d5-0ab2-460f-94de-29e3d88f5e6a)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_56_27](https://github.com/shubnimkar/Alpha-one/assets/46809421/2650956d-cc6c-4663-9856-d2e22979b56d)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_59_00](https://github.com/shubnimkar/Alpha-one/assets/46809421/367983a8-c73a-4961-9c23-8ece8c645fae)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_59_24](https://github.com/shubnimkar/Alpha-one/assets/46809421/4f326137-0f48-4184-96f6-977c87203847)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_59_31](https://github.com/shubnimkar/Alpha-one/assets/46809421/bcde73a8-b9b6-4219-9497-b300b6a32c53)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 15_59_38](https://github.com/shubnimkar/Alpha-one/assets/46809421/29025474-374d-4eda-bc2a-ec9c2915ec1f)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 16_00_24](https://github.com/shubnimkar/Alpha-one/assets/46809421/4476a881-d3ba-4bca-a4b4-77683bbe1e89)
![Windows Server 2016 (1) - VMware Workstation 01-07-2023 16_04_05](https://github.com/shubnimkar/Alpha-one/assets/46809421/ca5c5940-cc8e-4149-9487-245a55d8d1b0)

# MAN IN MIDDLE

disable policy on both
on kali
ettercap graphical

![Kali - VMware Workstation 01-07-2023 17_15_59](https://github.com/shubnimkar/Alpha-one/assets/46809421/b6d20272-e6c6-4c54-99e9-7e5cc569a181)
![Kali - VMware Workstation 01-07-2023 17_17_12](https://github.com/shubnimkar/Alpha-one/assets/46809421/80cac19b-0678-48cf-afaf-1d5be359aa46)
![Kali - VMware Workstation 01-07-2023 17_17_31](https://github.com/shubnimkar/Alpha-one/assets/46809421/37e6a8fb-ef52-4429-b409-5b4dc96e6363)
![Kali - VMware Workstation 01-07-2023 17_18_24](https://github.com/shubnimkar/Alpha-one/assets/46809421/ff5d8846-4bdf-4316-b976-435ed2459942)
![Kali - VMware Workstation 01-07-2023 17_20_31](https://github.com/shubnimkar/Alpha-one/assets/46809421/3226a700-ca34-4696-aec2-f36a7e26a68b)
   ![Kali - VMware Workstation 01-07-2023 17_20_52](https://github.com/shubnimkar/Alpha-one/assets/46809421/8920661d-e8d9-42bf-b28c-234e15e0b770)
![Kali - VMware Workstation 01-07-2023 17_21_14](https://github.com/shubnimkar/Alpha-one/assets/46809421/4c0b028d-9fe7-46e5-b152-ca3b72f3de5f)
![Kali - VMware Workstation 01-07-2023 17_30_07](https://github.com/shubnimkar/Alpha-one/assets/46809421/f628e4e5-3ab6-4771-ac2b-8fd7f6ea546b)
