//SolidityPractice
pragma solidity ^0.4.22;
pragma experimental ABIEncoderV2;

contract StringFunctions{
    string[] stringarrays = ["Koti","Rama","Murthy","Pandey","Medha"];
    string public concatedString = concat(stringarrays);
    
    function concat(string[] stringarray) public returns(string){
        bytes memory finalBytes;
        uint k=0;
        for(uint i=0;i<stringarray.length;i++){
            bytes memory currentElement = bytes(stringarray[i]);
            for(uint j=0;j<currentElement.length;j++) finalBytes[k++] = currentElement[j]; //Issue here
        }
        return string(finalBytes);
    }
}
