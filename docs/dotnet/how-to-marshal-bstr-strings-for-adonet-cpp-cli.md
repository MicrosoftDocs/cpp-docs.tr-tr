---
title: 'Nasıl yapılır: ADO.NET için BSTR dizelerini sıralama (C + +/ CLI) | Microsoft Docs'
ms.custom: get-started-article
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
ms.assetid: 5daf4d9e-6ae8-4604-908f-855e37c8d636
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 633b9d623a759caaee3aa6dcf2c93d95549927d3
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33136655"
---
# <a name="how-to-marshal-bstr-strings-for-adonet-ccli"></a>Nasıl Yapılır: ADO.NET İçin BSTR Dizelerini Sıralama (C++/CLI)
Bir COM dizesi eklemek nasıl gösterir (`BSTR`) bir veritabanı ve nasıl hazırlanacağını bir <xref:System.String?displayProperty=fullName> bir veritabanından bir `BSTR`.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir ADO.NET ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> nesnesi. Bu sınıf yerel C++ olduğuna dikkat edin `class` (kıyasla bir `ref class` veya `value class`). Bu, çünkü bu sınıf yerel koddan kullanmak istiyoruz ve yerel kodda yönetilen türler kullanamazsınız gereklidir. Bu sınıf tarafından belirtildiği şekilde CLR hedeflemek için derlenmiş `#pragma managed` sınıf bildiriminden önceki yönergesi. Bu yönerge hakkında daha fazla bilgi için bkz: [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).  
  
 Özel üye DatabaseClass sınıfının dikkat edin: `gcroot<DataTable ^> table`. Yerel türler yönetilen türler içeremez beri `gcroot` anahtar sözcüğü gereklidir. Daha fazla bilgi için `gcroot`, bkz: [nasıl yapılır: bildirimini işleme yerel türlerde](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Belirtildiği gibi yerel C++ kodu, bu örnekteki kod kalan `#pragma unmanaged` yönerge önceki `main`. Bu örnekte, biz DatabaseClass yeni bir örneğini oluşturma ve bir tablo oluşturun ve bazı tablosundaki satırları doldurmak için kendi yöntemleri çağırma. COM dizelerini veritabanı sütunu StringCol için olarak geçirilen unutmayın. Bulunan hazırlama işlevi kullanılarak yönetilen dizeler için sıralanmış DatabaseClass, bu dizeler <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanı. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> sıralama için kullanılan bir `BSTR` için bir <xref:System.String>ve yöntemi <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> sıralama için kullanılan bir <xref:System.String> için bir `BSTR`.  
  
> [!NOTE]
>  Tarafından ayrılan bellek <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> ya da çağrılmasıyla gerekir <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> veya `SysFreeString`.  
  
```  
// adonet_marshal_string_bstr.cpp  
// compile with: /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll  
#include <comdef.h>  
#include <gcroot.h>  
#include <iostream>  
using namespace std;  
  
#using <System.Data.dll>  
using namespace System;  
using namespace System::Data;  
using namespace System::Runtime::InteropServices;  
  
#define MAXCOLS 100  
  
#pragma managed  
class DatabaseClass  
{  
public:  
    DatabaseClass() : table(nullptr) { }  
  
    void AddRow(BSTR stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringBSTR(  
            (IntPtr)stringColValue);  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("StringCol",  
            Type::GetType("System.String"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(BSTR dataColumn, BSTR *values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringBSTR(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a BSTR.  
            values[i] = (BSTR)Marshal::StringToBSTR(  
                (String ^)rows[i][columnStr]).ToPointer();  
        }  
  
        return len;  
    }  
  
private:  
    // Using gcroot, you can use a managed type in  
    // a native class.  
    gcroot<DataTable ^> table;  
};  
  
#pragma unmanaged  
int main()  
{  
    // Create a table and add a few rows to it.  
    DatabaseClass *db = new DatabaseClass();  
    db->CreateAndPopulateTable();  
  
    BSTR str1 = SysAllocString(L"This is string 1.");  
    db->AddRow(str1);  
  
    BSTR str2 = SysAllocString(L"This is string 2.");  
    db->AddRow(str2);  
  
    // Now retrieve the rows and display their contents.  
    BSTR values[MAXCOLS];  
    BSTR str3 = SysAllocString(L"StringCol");  
    int len = db->GetValuesForColumn(  
        str3, values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToBSTR.  
        SysFreeString(values[i]);  
    }  
  
    SysFreeString(str1);  
    SysFreeString(str2);  
    SysFreeString(str3);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
  
-   Komut satırından Kodu derlemek için kod örneği adonet_marshal_string_native.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 ADO.NET ile ilgili güvenlik sorunları hakkında daha fazla bilgi için bkz: [ADO.NET uygulamaların güvenliğini sağlama](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET kullanarak veri erişim (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Birlikte çalışabilirlik](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)