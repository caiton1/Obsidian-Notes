Data structures that can be understood by the controller and the host

1. **Identify Namespace Data Structure**:

- This data structure is used to retrieve information about a specific namespace. The command to access this structure can use a specific Namespace Identifier (NSID) field.
- If the NSID is set to FFFFFFFFh, it provides an I/O Command Set Independent Identify Namespace data structure, which outlines common capabilities for the controller.

2. **Identify I/O Command Set Data Structure**:

- This structure is returned to the host for the controller specified in the Controller ID (CNTID) field. It provides details about the supported I/O command sets.

1. **Identify Controller Data Structure**:

- This data structure provides information about the controller processing the command. It includes various attributes about the controller itself.

2. **Submission Queue (SQ) Entry Structure**:
- SQID
- contains command identifier submissions cdw0.CID 
- Each entry in the Submission Queue contains a command to be issued to the controller, including all the necessary information to identify the command type and parameters.

3. **Completion Queue (CQ) Entry Structure**:

- Similar to the SQ structure, this structure allows the host to retrieve information about the completion status of a command previously submitted.

4. **Controller Identification**:

- Identifications related to the controller along with the status of queues are maintained via registers and specific data structures defined in the NVMe specification.








### FNA
Format NVM Attributes (FNA): This field indicates attributes for the Format NVM  
command.  

Bits 7:4 are reserved.

Bit 3: indicates whether the Format NVM command supports an NSID value set to  
FFFFFFFFh (all namespaces in control by controller). 
- If set to ‘1’, then the Format NVM command does not support an NSID  
value set to FFFFFFFFh. 
- If cleared to ‘0’, then the Format NVM command supports an  
NSID value set to FFFFFFFFh.  
- How might this flip/change/clear?  


Bit 2: indicates whether cryptographic erase is supported as part of the secure erase  
functionality.
- If set to ‘1’, then cryptographic erase is supported. 
- If cleared to ‘0’, then  cryptographic erase is not supported.  

Bit 1: indicates whether secure erase functionality applies to all namespaces in the NVM  
subsystem or is specific to a particular namespace. If set to ’1’, then any secure erase  
performed as part of a format operation results in a secure erase of all namespaces in  
the NVM subsystem. If cleared to ‘0’, then any secure erase performed as part of a  
format results in a secure erase of the particular namespace specified. If bit 3 is set to  
‘1’, then this bit shall be cleared to ‘0’.  

Bit 0: indicates whether the format operation (excluding secure erase) applies to all  
namespaces in the NVM subsystem or is specific to a particular namespace. 
- If set to  ‘1’, then all namespaces in the NVM subsystem shall be configured with the same  
attributes and a format (excluding secure erase) of any namespace results in a format  of all namespaces in the NVM subsystem. 
- If cleared to ‘0’, then the controller supports format on a per namespace basis. If bit 3 is set to ‘1’, then this bit shall be cleared to ‘0’
