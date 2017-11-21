---
title: "Nasıl yapılır: ADO.NET için bir VARIANT'ı sıralama (C + +/ CLI) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs: C++
helpviewer_keywords:
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
ms.assetid: 67a180a7-5691-48ab-8d85-7f75a68dde91
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 166116f54882048f3cd763b2f61e6b4fd56e5357
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="how-to-marshal-a-variant-for-adonet-ccli"></a>Nasıl yapılır: ADO.NET için bir VARIANT'ı Sıralama (C++/CLI)
Yerel ekleneceği gösterilmektedir `VARIANT` bir veritabanı ve nasıl hazırlanacağını bir <xref:System.Object?displayProperty=fullName> yerel bir veritabanından `VARIANT`.  
  
## <a name="example"></a>Örnek  
 Bu örnekte, bir ADO.NET ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> nesnesi. Bu sınıf yerel C++ olduğuna dikkat edin `class` (kıyasla bir `ref class` veya `value class`). Bu, çünkü bu sınıf yerel koddan kullanmak istiyoruz ve yerel kodda yönetilen türler kullanamazsınız gereklidir. Bu sınıf tarafından belirtildiği şekilde CLR hedeflemek için derlenmiş `#pragma managed` sınıf bildiriminden önceki yönergesi. Bu yönerge hakkında daha fazla bilgi için bkz: [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).  
  
 Özel üye DatabaseClass sınıfının dikkat edin: `gcroot<DataTable ^> table`. Yerel türler yönetilen türler içeremez beri `gcroot` anahtar sözcüğü gereklidir. Daha fazla bilgi için `gcroot`, bkz: [nasıl yapılır: bildirimini işleme yerel türlerde](../dotnet/how-to-declare-handles-in-native-types.md).  
  
 Belirtildiği gibi yerel C++ kodu, bu örnekteki kod kalan `#pragma unmanaged` yönerge önceki `main`. Bu örnekte, biz DatabaseClass yeni bir örneğini oluşturma ve bir tablo oluşturun ve bazı tablosundaki satırları doldurmak için kendi yöntemleri çağırma. Unutmayın, yerel `VARIANT` türleri olarak geçirilir ObjectCol veritabanı sütun değerleri. DatabaseClass, bunlar `VARIANT` türleri bulunan hazırlama işlevi kullanılarak yönetilen nesneler için sıralanmış <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanı. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> sıralama için kullanılan bir `VARIANT` için bir <xref:System.Object>ve yöntemi <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> sıralama için kullanılan bir <xref:System.Object> için bir `VARIANT`.  
  
```  
// adonet_marshal_variant.cpp  
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
  
    void AddRow(VARIANT *objectColValue)  
    {  
        // Add a row to the table.  
        DataRow ^row = table->NewRow();  
        row["ObjectCol"] = Marshal::GetObjectForNativeVariant(  
            IntPtr(objectColValue));  
        table->Rows->Add(row);  
    }  
  
    void CreateAndPopulateTable()  
    {  
        // Create a simple DataTable.  
        table = gcnew DataTable("SampleTable");  
  
        // Add a column of type String to the table.  
        DataColumn ^column1 = gcnew DataColumn("ObjectCol",  
            Type::GetType("System.Object"));  
        table->Columns->Add(column1);  
    }  
  
    int GetValuesForColumn(wchar_t *dataColumn, VARIANT *values,  
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
            // Marshal each column value from a managed object  
            // to a VARIANT.  
            Marshal::GetNativeVariantForObject(  
                rows[i][columnStr], IntPtr(&values[i]));  
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
  
    BSTR bstr1 = SysAllocString(L"This is a BSTR in a VARIANT.");  
    VARIANT v1;  
    v1.vt = VT_BSTR;  
    v1.bstrVal = bstr1;  
    db->AddRow(&v1);  
  
    int i = 42;  
    VARIANT v2;  
    v2.vt = VT_I4;  
    v2.lVal = i;  
    db->AddRow(&v2);  
  
    // Now retrieve the rows and display their contents.  
    VARIANT values[MAXCOLS];  
    int len = db->GetValuesForColumn(  
        L"ObjectCol", values, MAXCOLS);  
    for (int i = 0; i < len; i++)  
    {  
        switch (values[i].vt)  
        {  
            case VT_BSTR:  
                wcout << L"ObjectCol: " << values[i].bstrVal << endl;  
                break;  
            case VT_I4:  
                cout << "ObjectCol: " << values[i].lVal << endl;  
                break;  
            default:  
                break;  
        }  
  
    }  
  
    SysFreeString(bstr1);  
    delete db;  
  
    return 0;  
}  
```  
  
```Output  
ObjectCol: This is a BSTR in a VARIANT.  
ObjectCol: 42  
```  
  
## <a name="compiling-the-code"></a>Kod Derleniyor  
  
-   Komut satırından Kodu derlemek için kod örneği adonet_marshal_variant.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:  
  
    ```  
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp  
    ```  
  
## <a name="net-framework-security"></a>.NET Framework Güvenliği  
 ADO.NET ile ilgili güvenlik sorunları hakkında daha fazla bilgi için bkz: [ADO.NET uygulamaların güvenliğini sağlama](/dotnet/framework/data/adonet/securing-ado-net-applications).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 <xref:System.Runtime.InteropServices>   
 [ADO.NET kullanarak veri erişim (C + +/ CLI)](../dotnet/data-access-using-adonet-cpp-cli.md)   
 [ADO.NET](/dotnet/framework/data/adonet/index)   
 [Birlikte çalışabilirlik](http://msdn.microsoft.com/en-us/afcc2e7d-3f32-48d2-8141-1c42acf29084)   
 [Yerel ve.NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)