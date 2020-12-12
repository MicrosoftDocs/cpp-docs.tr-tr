---
description: 'Hakkında daha fazla bilgi edinin: ADO.NET kullanarak veri erişimi (C++/CLı)'
title: ADO.NET Kullanarak Veri Erişimi (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- ADO.NET [C++]
- .NET Framework [C++], data access
- databases [C++], accessing in C++
- data access [C++], ADO.NET
- data [C++], ADO.NET
- native strings [C++]
- ADO.NET [C++], marshaling ANSI strings
- strings [C++], ADO.NET
- BSTRs, strings
- ADO.NET [C++], marshaling BSTR strings
- strings [C++], marshaling BSTR strings
- ADO.NET [C++], marshaling Unicode strings
- Unicode [C++], strings
- strings [C++], Unicode
- VARIANT, marshaling
- ADO.NET [C++], marshaling VARIANT types
- VARIANT
- SAFEARRAY, marshaling
- ADO.NET [C++], marshaling SAFEARRAY types
ms.assetid: b0cd987d-1ea7-4f76-ba01-cbd52503d06d
ms.openlocfilehash: 93af8a8a2dc4ebc8d9fe6073b9f3a70f4868bee8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124273"
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET Kullanarak Veri Erişimi (C++/CLI)

ADO.NET, veri erişimi için .NET Framework API 'sidir ve önceki veri erişimi çözümleri tarafından eşleşmeyen güç ve kullanım kolaylığı sağlar. Bu bölümde, yerel türleri hazırlama gibi Visual C++ kullanıcılara özgü olan ADO.NET ile ilgili bazı sorunlar açıklanmaktadır.

ADO.NET, ortak dil çalışma zamanı (CLR) altında çalışır. Bu nedenle, ADO.NET ile etkileşen tüm uygulamalar CLR 'yi de hedeflemelidir. Ancak, yerel uygulamaların ADO.NET kullanmayacağınız anlamına gelmez. Bu örnekler, yerel koddan bir ADO.NET veritabanıyla nasıl etkileşim kuracağınızı gösterir.

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a> ADO.NET için ANSI Dizelerini Sıralama

Bir veritabanına yerel bir dizenin () nasıl ekleneceğini `char *` ve bir <xref:System.String?displayProperty=fullName> veritabanından yerel dizeye nasıl hazırlanacağını gösterir.

### <a name="example"></a>Örnek

Bu örnekte, bir ADO.NET nesnesi ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> . Bu sınıfın yerel bir C++ **`class`** (veya ile karşılaştırıldığında) olduğunu unutmayın **`ref class`** **`value class`** . Bu sınıfı yerel koddan kullanmak istediğimiz ve yerel kodda yönetilen türleri kullandığımız için bu gereklidir. Bu sınıf, `#pragma managed` Sınıf bildiriminden önceki yönergeyle gösterildiği gıbı clr 'yi hedeflemek için derlenir. Bu yönergeyle ilgili daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).

DatabaseClass sınıfının özel üyesini Note: `gcroot<DataTable ^> table` . Yerel türler yönetilen türleri içeremediğinden `gcroot` anahtar sözcüğü gereklidir. Hakkında daha fazla bilgi için `gcroot` bkz. [nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md).

Yukarıdaki yönergeyle gösterildiği gibi bu örnekteki kodun geri kalanı yerel C++ kodudur `#pragma unmanaged` `main` . Bu örnekte, DatabaseClass 'ın yeni bir örneğini oluşturuyor ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırmak istiyoruz. Yerel C++ dizelerinin, veritabanı sütunu StringCol için değer olarak geçtiğini unutmayın. DatabaseClass içinde, bu dizeler ad alanında bulunan sıralama işlevi kullanılarak yönetilen dizelere sıralanır <xref:System.Runtime.InteropServices?displayProperty=fullName> . Özellikle, yöntemi <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> ' a ' a sıralamak için kullanılır `char *` <xref:System.String> ve yöntemi bir <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> öğesine sıralamak için kullanılır <xref:System.String> `char *` .

> [!NOTE]
> Tarafından ayrılan bellek, ya <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> da çağırarak serbest bırakılmalıdır <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> `GlobalFree` .

```cpp
// adonet_marshal_string_native.cpp
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

    void AddRow(char *stringColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        row["StringCol"] = Marshal::PtrToStringAnsi(
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

    int GetValuesForColumn(char *dataColumn, char **values,
        int valuesLength)
    {
        // Marshal the name of the column to a managed
        // String.
        String ^columnStr = Marshal::PtrToStringAnsi(
                (IntPtr)dataColumn);

        // Get all rows in the table.
        array<DataRow ^> ^rows = table->Select();
        int len = rows->Length;
        len = (len > valuesLength) ? valuesLength : len;
        for (int i = 0; i < len; i++)
        {
            // Marshal each column value from a managed string
            // to a char *.
            values[i] = (char *)Marshal::StringToHGlobalAnsi(
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
    db->AddRow("This is string 1.");
    db->AddRow("This is string 2.");

    // Now retrieve the rows and display their contents.
    char *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        "StringCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        cout << "StringCol: " << values[i] << endl;

        // Deallocate the memory allocated using
        // Marshal::StringToHGlobalAnsi.
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

### <a name="compiling-the-code"></a>Kod Derleniyor

- Kodu komut satırından derlemek için, kod örneğini adonet_marshal_string_native. cpp adlı bir dosyaya kaydedin ve aşağıdaki ifadeyi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a> ADO.NET için BSTR dizelerini sıralama

Bir veritabanına COM dizesinin () nasıl ekleneceğini `BSTR` ve bir veritabanından bir veritabanından nasıl hazırlanacağını gösterir <xref:System.String?displayProperty=fullName> `BSTR` .

### <a name="example"></a>Örnek

Bu örnekte, bir ADO.NET nesnesi ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> . Bu sınıfın yerel bir C++ **`class`** (veya ile karşılaştırıldığında) olduğunu unutmayın **`ref class`** **`value class`** . Bu sınıfı yerel koddan kullanmak istediğimiz ve yerel kodda yönetilen türleri kullandığımız için bu gereklidir. Bu sınıf, `#pragma managed` Sınıf bildiriminden önceki yönergeyle gösterildiği gıbı clr 'yi hedeflemek için derlenir. Bu yönergeyle ilgili daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).

DatabaseClass sınıfının özel üyesini Note: `gcroot<DataTable ^> table` . Yerel türler yönetilen türleri içeremediğinden `gcroot` anahtar sözcüğü gereklidir. Hakkında daha fazla bilgi için `gcroot` bkz. [nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md).

Yukarıdaki yönergeyle gösterildiği gibi bu örnekteki kodun geri kalanı yerel C++ kodudur `#pragma unmanaged` `main` . Bu örnekte, DatabaseClass 'ın yeni bir örneğini oluşturuyor ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırmak istiyoruz. COM dizelerinin, veritabanı sütunu StringCol için değer olarak geçtiğini unutmayın. DatabaseClass içinde, bu dizeler ad alanında bulunan sıralama işlevi kullanılarak yönetilen dizelere sıralanır <xref:System.Runtime.InteropServices?displayProperty=fullName> . Özellikle, yöntemi <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> ' a ' a sıralamak için kullanılır `BSTR` <xref:System.String> ve yöntemi bir <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> öğesine sıralamak için kullanılır <xref:System.String> `BSTR` .

> [!NOTE]
> Tarafından ayrılan bellek, ya <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> da çağırarak serbest bırakılmalıdır <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> `SysFreeString` .

``` cpp
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

### <a name="compiling-the-code"></a>Kod Derleniyor

- Kodu komut satırından derlemek için, kod örneğini adonet_marshal_string_native. cpp adlı bir dosyaya kaydedin ve aşağıdaki ifadeyi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a> ADO.NET için Unicode dizelerini sıralama

Bir veritabanına yerel Unicode dizesinin () nasıl ekleneceğini `wchar_t *` ve bir <xref:System.String?displayProperty=fullName> veritabanından yerel Unicode dizesine nasıl hazırlanacağını gösterir.

### <a name="example"></a>Örnek

Bu örnekte, bir ADO.NET nesnesi ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> . Bu sınıfın yerel bir C++ **`class`** (veya ile karşılaştırıldığında) olduğunu unutmayın **`ref class`** **`value class`** . Bu sınıfı yerel koddan kullanmak istediğimiz ve yerel kodda yönetilen türleri kullandığımız için bu gereklidir. Bu sınıf, `#pragma managed` Sınıf bildiriminden önceki yönergeyle gösterildiği gıbı clr 'yi hedeflemek için derlenir. Bu yönergeyle ilgili daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).

DatabaseClass sınıfının özel üyesini Note: `gcroot<DataTable ^> table` . Yerel türler yönetilen türleri içeremediğinden `gcroot` anahtar sözcüğü gereklidir. Hakkında daha fazla bilgi için `gcroot` bkz. [nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md).

Yukarıdaki yönergeyle gösterildiği gibi bu örnekteki kodun geri kalanı yerel C++ kodudur `#pragma unmanaged` `main` . Bu örnekte, DatabaseClass 'ın yeni bir örneğini oluşturuyor ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırmak istiyoruz. Unicode C++ dizelerinin, veritabanı sütunu StringCol için değer olarak geçtiğini unutmayın. DatabaseClass içinde, bu dizeler ad alanında bulunan sıralama işlevi kullanılarak yönetilen dizelere sıralanır <xref:System.Runtime.InteropServices?displayProperty=fullName> . Özellikle, yöntemi <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> ' a ' a sıralamak için kullanılır `wchar_t *` <xref:System.String> ve yöntemi bir <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> öğesine sıralamak için kullanılır <xref:System.String> `wchar_t *` .

> [!NOTE]
> Tarafından ayrılan bellek, ya <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> da çağırarak serbest bırakılmalıdır <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> `GlobalFree` .

```cpp
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

### <a name="compiling-the-code"></a>Kod Derleniyor

- Kodu komut satırından derlemek için, kod örneğini adonet_marshal_string_wide. cpp adlı bir dosyaya kaydedin ve aşağıdaki ifadeyi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a> ADO.NET için bir varyant sıralaması

Bir veritabanına yerel olarak nasıl ekleneceğini `VARIANT` ve bir veritabanından yerel olarak nasıl hazırlanacağını gösterir <xref:System.Object?displayProperty=fullName> `VARIANT` .

### <a name="example"></a>Örnek

Bu örnekte, bir ADO.NET nesnesi ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> . Bu sınıfın yerel bir C++ **`class`** (veya ile karşılaştırıldığında) olduğunu unutmayın **`ref class`** **`value class`** . Bu sınıfı yerel koddan kullanmak istediğimiz ve yerel kodda yönetilen türleri kullandığımız için bu gereklidir. Bu sınıf, `#pragma managed` Sınıf bildiriminden önceki yönergeyle gösterildiği gıbı clr 'yi hedeflemek için derlenir. Bu yönergeyle ilgili daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).

DatabaseClass sınıfının özel üyesini Note: `gcroot<DataTable ^> table` . Yerel türler yönetilen türleri içeremediğinden `gcroot` anahtar sözcüğü gereklidir. Hakkında daha fazla bilgi için `gcroot` bkz. [nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md).

Yukarıdaki yönergeyle gösterildiği gibi bu örnekteki kodun geri kalanı yerel C++ kodudur `#pragma unmanaged` `main` . Bu örnekte, DatabaseClass 'ın yeni bir örneğini oluşturuyor ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırmak istiyoruz. Yerel `VARIANT` türlerin, ObjectCol veritabanı sütunu için değer olarak geçtiğini unutmayın. DatabaseClass içinde, bu `VARIANT` türler ad alanında bulunan sıralama işlevi kullanılarak yönetilen nesneler için sıralanır <xref:System.Runtime.InteropServices?displayProperty=fullName> . Özellikle, yöntemi <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> ' a ' a sıralamak için kullanılır `VARIANT` <xref:System.Object> ve yöntemi bir <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> öğesine sıralamak için kullanılır <xref:System.Object> `VARIANT` .

```cpp
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

### <a name="compiling-the-code"></a>Kod Derleniyor

- Kodu komut satırından derlemek için, kod örneğini adonet_marshal_variant. cpp adlı bir dosyaya kaydedin ve aşağıdaki ifadeyi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a> ADO.NET için bir SAFEARRAY sıralaması

Bir veritabanına yerel olarak nasıl ekleneceğini `SAFEARRAY` ve yönetilen bir dizinin veritabanından yerel olarak nasıl hazırlanacağını gösterir `SAFEARRAY` .

### <a name="example"></a>Örnek

Bu örnekte, bir ADO.NET nesnesi ile etkileşim kurmak için DatabaseClass sınıfı oluşturulur <xref:System.Data.DataTable> . Bu sınıfın yerel bir C++ **`class`** (veya ile karşılaştırıldığında) olduğunu unutmayın **`ref class`** **`value class`** . Bu sınıfı yerel koddan kullanmak istediğimiz ve yerel kodda yönetilen türleri kullandığımız için bu gereklidir. Bu sınıf, `#pragma managed` Sınıf bildiriminden önceki yönergeyle gösterildiği gıbı clr 'yi hedeflemek için derlenir. Bu yönergeyle ilgili daha fazla bilgi için bkz. [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md).

DatabaseClass sınıfının özel üyesini Note: `gcroot<DataTable ^> table` . Yerel türler yönetilen türleri içeremediğinden `gcroot` anahtar sözcüğü gereklidir. Hakkında daha fazla bilgi için `gcroot` bkz. [nasıl yapılır: yerel türlerde işleyicileri bildirme](../dotnet/how-to-declare-handles-in-native-types.md).

Yukarıdaki yönergeyle gösterildiği gibi bu örnekteki kodun geri kalanı yerel C++ kodudur `#pragma unmanaged` `main` . Bu örnekte, DatabaseClass 'ın yeni bir örneğini oluşturuyor ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırmak istiyoruz. Yerel `SAFEARRAY` türlerin ArrayIntsCol veritabanı sütunu için değer olarak geçtiğini unutmayın. DatabaseClass içinde, bu `SAFEARRAY` türler ad alanında bulunan sıralama işlevi kullanılarak yönetilen nesneler için sıralanır <xref:System.Runtime.InteropServices?displayProperty=fullName> . Özellikle, yöntemi, <xref:System.Runtime.InteropServices.Marshal.Copy%2A> bir dizi `SAFEARRAY` tamsayının yönetilen bir dizisini sıralamak için kullanılır ve yöntemi, yönetilen bir <xref:System.Runtime.InteropServices.Marshal.Copy%2A> tamsayılar dizisini bir ile sıralamak için kullanılır `SAFEARRAY` .

```cpp
// adonet_marshal_safearray.cpp
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

    void AddRow(SAFEARRAY *arrayIntsColValue)
    {
        // Add a row to the table.
        DataRow ^row = table->NewRow();
        int len = arrayIntsColValue->rgsabound[0].cElements;
        array<int> ^arr = gcnew array<int>(len);

        int *pData;
        SafeArrayAccessData(arrayIntsColValue, (void **)&pData);
        Marshal::Copy(IntPtr(pData), arr, 0, len);
        SafeArrayUnaccessData(arrayIntsColValue);

        row["ArrayIntsCol"] = arr;
        table->Rows->Add(row);
    }

    void CreateAndPopulateTable()
    {
        // Create a simple DataTable.
        table = gcnew DataTable("SampleTable");

        // Add a column of type String to the table.
        DataColumn ^column1 = gcnew DataColumn("ArrayIntsCol",
            Type::GetType("System.Int32[]"));
        table->Columns->Add(column1);
    }

    int GetValuesForColumn(wchar_t *dataColumn, SAFEARRAY **values,
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
            // Marshal each column value from a managed array
            // of Int32s to a SAFEARRAY of type VT_I4.
            values[i] = SafeArrayCreateVector(VT_I4, 0, 10);
            int *pData;
            SafeArrayAccessData(values[i], (void **)&pData);
            Marshal::Copy((array<int> ^)rows[i][columnStr], 0,
                IntPtr(pData), 10);
            SafeArrayUnaccessData(values[i]);
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

    // Create a standard array.
    int originalArray[] = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };

    // Create a SAFEARRAY.
    SAFEARRAY *psa;
    psa = SafeArrayCreateVector(VT_I4, 0, 10);

    // Copy the data from the original array to the SAFEARRAY.
    int *pData;
    HRESULT hr = SafeArrayAccessData(psa, (void **)&pData);
    memcpy(pData, &originalArray, 40);
    SafeArrayUnaccessData(psa);
    db->AddRow(psa);

    // Now retrieve the rows and display their contents.
    SAFEARRAY *values[MAXCOLS];
    int len = db->GetValuesForColumn(
        L"ArrayIntsCol", values, MAXCOLS);
    for (int i = 0; i < len; i++)
    {
        int *pData;
        SafeArrayAccessData(values[i], (void **)&pData);
        for (int j = 0; j < 10; j++)
        {
            cout << pData[j] << " ";
        }
        cout << endl;
        SafeArrayUnaccessData(values[i]);

        // Deallocate the memory allocated using
        // SafeArrayCreateVector.
        SafeArrayDestroy(values[i]);
    }

    SafeArrayDestroy(psa);
    delete db;

    return 0;
}
```

```Output
0 1 2 3 4 5 6 7 8 9
```

### <a name="compiling-the-code"></a>Kod Derleniyor

- Kodu komut satırından derlemek için, kod örneğini adonet_marshal_safearray. cpp adlı bir dosyaya kaydedin ve aşağıdaki ifadeyi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework Güvenliği

ADO.NET ile ilgili güvenlik sorunları hakkında daha fazla bilgi için bkz. [ADO.NET uygulamalarının güvenliğini sağlama](/dotnet/framework/data/adonet/securing-ado-net-applications).

## <a name="related-sections"></a>İlgili Bölümler

|Section|Açıklama|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|.NET programcıya veri erişim hizmetleri sunan bir sınıf kümesi olan ADO.NET genel bir bakış sunar.|

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Yerel ve .NET birlikte çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[Birlikte çalışabilirlik](/dotnet/framework/interop/index)
