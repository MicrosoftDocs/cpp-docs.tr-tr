---
title: "Nasıl yapılır: ADO.NET için Unicode dizeleri sıralama (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
ms.assetid: 1da090ff-6b53-40be-841f-dc79dfe8ba10
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 65e030f0ba5d59653612b61246fbd5f4e39b9c96
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-unicode-strings-for-adonet-ccli"></a>Nasıl Yapılır: ADO.NET İçin Unicode Dizeleri Sıralama (C++/CLI)
Yerel bir UNICODE dizesi eklemek nasıl gösterir (`wchar_t *`) bir veritabanı ve nasıl hazırlanacağını bir <xref:System.String?displayProperty=fullName> bir veritabanından yerel bir UNICODE dizesi.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir ADO.NET ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> nesnesi. Bu sınıf yerel C++ olduğuna dikkat edin `class` (kıyasla bir `ref class` veya `value class`). Bu, çünkü bu sınıf yerel koddan kullanmak istiyoruz ve yerel kodda yönetilen türler kullanamazsınız gereklidir. Bu sınıf tarafından belirtildiği şekilde CLR hedeflemek için derlenmiş `#pragma managed` sınıf bildiriminden önceki yönergesi. Bu yönerge hakkında daha fazla bilgi için bkz: [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).  
  
 Özel üye DatabaseClass sınıfının dikkat edin: `gcroot<DataTable ^> table`. Yerel türler yönetilen türler içeremez beri `gcroot` anahtar sözcüğü gereklidir. Daha fazla bilgi için `gcroot`, bkz: [nasıl yapılır: bildirimini işleme yerel türlerde](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Belirtildiği gibi yerel C++ kodu, bu örnekteki kod kalan `#pragma unmanaged` yönerge önceki `main`. Bu örnekte, biz DatabaseClass yeni bir örneğini oluşturma ve bir tablo oluşturun ve bazı tablosundaki satırları doldurmak için kendi yöntemleri çağırma. Unicode C++ dizelerinin veritabanı sütunu StringCol için olarak geçirilen unutmayın. Bulunan hazırlama işlevi kullanılarak yönetilen dizeler için sıralanmış DatabaseClass, bu dizeler <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanı. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> sıralama için kullanılan bir `wchar_t *` için bir <xref:System.String>ve yöntemi <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> sıralama için kullanılan bir <xref:System.String> için bir `wchar_t *`.  
  
> [!NOTE]
>  Tarafından ayrılan bellek <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> ya da çağrılmasıyla gerekir <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> veya `GlobalFree`.  
  
```  
// adonet_marshal_string_wide.cpp  
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
  
    void AddRow(wchar_t *stringColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["StringCol"] = Marshal::PtrToStringUni(  
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
  
    int GetValuesForColumn(wchar_t *dataColumn, wchar_t **values,  
        int valuesLength)  
    {  
        // Marshal the name of the column to a managed  
        // String.  
        String ^columnStr = Marshal::PtrToStringUni(  
                (IntPtr)dataColumn);  
  
        // Get all rows in the table.  
        array<DataRow ^> ^rows = table->Select();  
        int len = rows->Length;  
        len = (len > valuesLength) ? valuesLength : len;  
        for (int i = 0; i < len; i++)  
        {  
            // Marshal each column value from a managed string  
            // to a wchar_t *.  
            values[i] = (wchar_t *)Marshal::StringToHGlobalUni(  
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
    db->AddRow(L"This is string 1.");  
    db->AddRow(L"This is string 2.");  
  
    // Now retrieve the rows and display their contents.  
    wchar_t *values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"StringCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        wcout << "StringCol: " << values[i] << endl;  
  
        // Deallocate the memory allocated using  
        // Marshal::StringToHGlobalUni.  
        GlobalFree(values[i]);  
    }  
  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
StringCol: This is string 1.  
StringCol: This is string 2.  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
  
-   Komut satırından Kodu derlemek için kod örneği adonet_marshal_string_wide.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 ADO.NET ile ilgili güvenlik sorunları hakkında daha fazla bilgi için bkz: [ADO.NET uygulamaların güvenliğini sağlama](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET kullanarak veri erişim (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Birlikte çalışabilirlik](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Yerel ve.NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)