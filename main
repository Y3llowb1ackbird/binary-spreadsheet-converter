/**
 * Public controller function for converting a spreadsheet to binary
 */
function convertSpreadsheetToBinary(){


  const ss = SpreadsheetApp.getActiveSpreadsheet();
  const sheets = ss.getSheets();

  // Iterate over each sheet and convert it to binary.
  for (i in sheets){

    convertSheetToBinary_(sheets[i]);

  }

  // Convert spreadsheet name to binary.
  let ss_name = ss.getName();
  ss.rename(convertStringToBinary_(ss_name));


}

/**
 * Private helper function to convert a given sheet to binary.
 * @param {Sheet} the sheet to convert to binary
 */
function convertSheetToBinary_(sheet){

  // Read sheet data
  let sheet_data_range = sheet.getDataRange();
  let sheet_values = sheet_data_range.getValues();

  let i = 0;
  let j = 0;


  // Iterate over sheet values
  while (i < sheet_values.length){

    j = 0;
    while (j < sheet_values[i].length){

      sheet_values[i][j] = convertStringToBinary_(sheet_values[i][j]); // convert cell data to binary

      j++;

    }
    i++;

  }

  // Write the modified values to the sheet
  sheet_data_range.setValues(sheet_values);

  // Convert the sheet name to binary.
  let sheetName = sheet.getName();
  sheetName = convertStringToBinary_(sheetName);
  sheet.setName(sheetName);

}

/**
 * Private helper function to convert a given character to binary.
 * @param {String} the character to convert to binary
 * @return {String} the character in binary representation
 */
function convertCharToBinary_(input_char){

  let output_char = "";
  let bin_char = input_char.charCodeAt().toString(2); // get binary representation of input character

  output_char = bin_char;

  // If binary representation is less than 8 bits, add leading zeros.
  while (output_char.length < 8){

    output_char = "0" + output_char;

  }

  return output_char;


}

/**
 * Private helper function to convert a given string to binary.
 * @param {String} the string to convert to binary
 * @return {String} the string in binary representation
 */
function convertStringToBinary_(input_string){

  let outputString = "";

  let char;
  for(i in input_string){

    char = input_string[i];                    // get next character
    outputString += convertCharToBinary_(char); // convert character to binary and append to output string.

  }


  return outputString;


}
