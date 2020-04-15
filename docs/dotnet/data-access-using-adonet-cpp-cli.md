---
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
ms.openlocfilehash: 35633449c4c01f5c103dcd54b81c0d6aa7c08cdc
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364418"
---
# <a name="data-access-using-adonet-ccli"></a>ADO.NET Kullanarak Veri Erişimi (C++/CLI)

ADO.NET veri erişimi için .NET Framework API'dir ve önceki veri erişim çözümleriyle eşleşmeden güç ve kullanım kolaylığı sağlar. Bu bölümde, görsel C++ kullanıcılarına özgü ADO.NET içeren bazı sorunlar açıklanmaktadır(örneğin, yerel türleri mareşallik etmek).

ADO.NET Ortak Dil Çalışma Süresi (CLR) altında çalışır. Bu nedenle, ADO.NET ile etkileşimedebilen herhangi bir uygulama da CLR hedef gerekir. Ancak, bu yerel uygulamalar ADO.NET kullanamazsınız anlamına gelmez. Bu örnekler, yerel koddan ADO.NET bir veritabanıyla nasıl etkileşimde bulunacaklarını gösterecektir.

## <a name="marshal-ansi-strings-for-adonet"></a><a name="marshal_ansi"></a>ADO.NET için Mareşal ANSI Dizeleri

Veritabanına nasıl bir yerel`char *`dize ( ) ekleyeceğinive bir veritabanından yerel bir dize için nasıl <xref:System.String?displayProperty=fullName> bir a'yı nasıl yazılabildiğini gösterir.

### <a name="example"></a>Örnek

Bu örnekte, sınıf DatabaseClass ADO.NET <xref:System.Data.DataTable> bir nesne ile etkileşim için oluşturulur. Bu sınıfın yerel bir C++ `class` olduğunu unutmayın `ref class` `value class`(a veya ile karşılaştırıldığında). Bu, bu sınıfı yerel koddan kullanmak istediğimizden ve yerel kodda yönetilen türleri kullanamadığınız için gereklidir. Bu sınıf, sınıf bildiriminden önceki yönergede `#pragma managed` belirtildiği gibi CLR'yi hedeflemek üzere derlenecektir. Bu yönerge hakkında daha fazla bilgi için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)bkz.

DatabaseClass sınıfının özel üyesine `gcroot<DataTable ^> table`dikkat edin: . Yerel türler yönetilen türleri içeremediğinden, `gcroot` anahtar kelime gereklidir. Daha fazla `gcroot`bilgi için [bkz: Yerel Türlerde Tanıtıcıları Bildirin.](../dotnet/how-to-declare-handles-in-native-types.md)

Bu örnekteki kodun geri kalanı, önceki `#pragma unmanaged` `main`yönergede belirtildiği gibi yerel C++ kodudur. Bu örnekte, VeritabanıSınıfı'nın yeni bir örneğini oluşturuyoruz ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırıyoruz. Yerel C++ dizelerinin veritabanı sütunu StringCol için değer olarak geçirildiğini unutmayın. DatabaseClass içinde, bu dizeleri <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanında bulunan mareşal işlevi kullanılarak yönetilen dizeleri marshaled. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.PtrToStringAnsi%2A> a'dan `char *` <xref:System.String>a'ya mareşal olarak kullanılır <xref:System.String> ve `char *`yöntem <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> a'dan a'ya mareşal olarak kullanılır.

> [!NOTE]
> Tarafından <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalAnsi%2A> ayrılan bellek ya da <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> `GlobalFree`' yı arayarak devreden olmalıdır.

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

- Kodu komut satırından derlemek için kod örneğini adonet_marshal_string_native.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-bstr-strings-for-adonet"></a><a name="marshal_bstr"></a>ADO.NET için Mareşal BSTR Dizeleri

Com dizesini ( )`BSTR`veritabanına nasıl ekleyeceğinive <xref:System.String?displayProperty=fullName> bir veritabanından `BSTR`bir veritabanına nasıl marshal yapılacağını gösterir.

### <a name="example"></a>Örnek

Bu örnekte, sınıf DatabaseClass ADO.NET <xref:System.Data.DataTable> bir nesne ile etkileşim için oluşturulur. Bu sınıfın yerel bir C++ `class` olduğunu unutmayın `ref class` `value class`(a veya ile karşılaştırıldığında). Bu, bu sınıfı yerel koddan kullanmak istediğimizden ve yerel kodda yönetilen türleri kullanamadığınız için gereklidir. Bu sınıf, sınıf bildiriminden önceki yönergede `#pragma managed` belirtildiği gibi CLR'yi hedeflemek üzere derlenecektir. Bu yönerge hakkında daha fazla bilgi için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)bkz.

DatabaseClass sınıfının özel üyesine `gcroot<DataTable ^> table`dikkat edin: . Yerel türler yönetilen türleri içeremediğinden, `gcroot` anahtar kelime gereklidir. Daha fazla `gcroot`bilgi için [bkz: Yerel Türlerde Tanıtıcıları Bildirin.](../dotnet/how-to-declare-handles-in-native-types.md)

Bu örnekteki kodun geri kalanı, önceki `#pragma unmanaged` `main`yönergede belirtildiği gibi yerel C++ kodudur. Bu örnekte, VeritabanıSınıfı'nın yeni bir örneğini oluşturuyoruz ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırıyoruz. COM dizeleri veritabanı sütunStringCol için değer olarak geçiriliyor unutmayın. DatabaseClass içinde, bu dizeleri <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanında bulunan mareşal işlevi kullanılarak yönetilen dizeleri marshaled. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.PtrToStringBSTR%2A> a'dan `BSTR` <xref:System.String>a'ya mareşal olarak kullanılır <xref:System.String> ve `BSTR`yöntem <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> a'dan a'ya mareşal olarak kullanılır.

> [!NOTE]
> Tarafından <xref:System.Runtime.InteropServices.Marshal.StringToBSTR%2A> ayrılan bellek ya da <xref:System.Runtime.InteropServices.Marshal.FreeBSTR%2A> `SysFreeString`' yı arayarak devreden olmalıdır.

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

- Kodu komut satırından derlemek için kod örneğini adonet_marshal_string_native.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_native.cpp
    ```

## <a name="marshal-unicode-strings-for-adonet"></a><a name="marshal_unicode"></a>ADO.NET için Mareşal Unicode Dizeleri

Bir veritabanına yerel Unicode dizesi ()`wchar_t *`nasıl ekleyeceğinive bir <xref:System.String?displayProperty=fullName> veritabanından yerel Unicode dizesine nasıl bir a'nın nasıl marshal yapılacağını gösterir.

### <a name="example"></a>Örnek

Bu örnekte, sınıf DatabaseClass ADO.NET <xref:System.Data.DataTable> bir nesne ile etkileşim için oluşturulur. Bu sınıfın yerel bir C++ `class` olduğunu unutmayın `ref class` `value class`(a veya ile karşılaştırıldığında). Bu, bu sınıfı yerel koddan kullanmak istediğimizden ve yerel kodda yönetilen türleri kullanamadığınız için gereklidir. Bu sınıf, sınıf bildiriminden önceki yönergede `#pragma managed` belirtildiği gibi CLR'yi hedeflemek üzere derlenecektir. Bu yönerge hakkında daha fazla bilgi için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)bkz.

DatabaseClass sınıfının özel üyesine `gcroot<DataTable ^> table`dikkat edin: . Yerel türler yönetilen türleri içeremediğinden, `gcroot` anahtar kelime gereklidir. Daha fazla `gcroot`bilgi için [bkz: Yerel Türlerde Tanıtıcıları Bildirin.](../dotnet/how-to-declare-handles-in-native-types.md)

Bu örnekteki kodun geri kalanı, önceki `#pragma unmanaged` `main`yönergede belirtildiği gibi yerel C++ kodudur. Bu örnekte, VeritabanıSınıfı'nın yeni bir örneğini oluşturuyoruz ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırıyoruz. Unicode C++ dizelerinin veritabanı sütunu StringCol için değer olarak geçirildiğini unutmayın. DatabaseClass içinde, bu dizeleri <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanında bulunan mareşal işlevi kullanılarak yönetilen dizeleri marshaled. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.PtrToStringUni%2A> a'dan `wchar_t *` <xref:System.String>a'ya mareşal olarak kullanılır <xref:System.String> ve `wchar_t *`yöntem <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> a'dan a'ya mareşal olarak kullanılır.

> [!NOTE]
> Tarafından <xref:System.Runtime.InteropServices.Marshal.StringToHGlobalUni%2A> ayrılan bellek ya da <xref:System.Runtime.InteropServices.Marshal.FreeHGlobal%2A> `GlobalFree`' yı arayarak devreden olmalıdır.

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

- Kodu komut satırından derlemek için kod örneğini adonet_marshal_string_wide.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_string_wide.cpp
    ```

## <a name="marshal-a-variant-for-adonet"></a><a name="marshal_variant"></a>Mareşal ADO.NET için bir VARYANT

Bir veritabanına nasıl `VARIANT` bir veri tabanına bir <xref:System.Object?displayProperty=fullName> yerel ekleyeceğini `VARIANT`ve bir veritabanından bir veritabanına nasıl bir a'yı nasıl yazabildiğini gösterir.

### <a name="example"></a>Örnek

Bu örnekte, sınıf DatabaseClass ADO.NET <xref:System.Data.DataTable> bir nesne ile etkileşim için oluşturulur. Bu sınıfın yerel bir C++ `class` olduğunu unutmayın `ref class` `value class`(a veya ile karşılaştırıldığında). Bu, bu sınıfı yerel koddan kullanmak istediğimizden ve yerel kodda yönetilen türleri kullanamadığınız için gereklidir. Bu sınıf, sınıf bildiriminden önceki yönergede `#pragma managed` belirtildiği gibi CLR'yi hedeflemek üzere derlenecektir. Bu yönerge hakkında daha fazla bilgi için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)bkz.

DatabaseClass sınıfının özel üyesine `gcroot<DataTable ^> table`dikkat edin: . Yerel türler yönetilen türleri içeremediğinden, `gcroot` anahtar kelime gereklidir. Daha fazla `gcroot`bilgi için [bkz: Yerel Türlerde Tanıtıcıları Bildirin.](../dotnet/how-to-declare-handles-in-native-types.md)

Bu örnekteki kodun geri kalanı, önceki `#pragma unmanaged` `main`yönergede belirtildiği gibi yerel C++ kodudur. Bu örnekte, VeritabanıSınıfı'nın yeni bir örneğini oluşturuyoruz ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırıyoruz. Veritabanı sütunu ObjectCol için değer olarak yerel `VARIANT` türlerin geçirildiğini unutmayın. DatabaseClass içinde, `VARIANT` bu tür <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanında bulunan mareşal işlevi kullanılarak yönetilen nesnelere marshaled. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.GetObjectForNativeVariant%2A> bir `VARIANT` <xref:System.Object>mareşal için kullanılır <xref:System.Runtime.InteropServices.Marshal.GetNativeVariantForObject%2A> , ve yöntem <xref:System.Object> bir `VARIANT`mareşal için kullanılır .

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

- Kodu komut satırından derlemek için kod örneğini adonet_marshal_variant.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_variant.cpp
    ```

## <a name="marshal-a-safearray-for-adonet"></a><a name="marshal_safearray"></a>ADO.NET için bir SAFEARRAY Mareşal

Bir veritabanına nasıl `SAFEARRAY` bir yerel ekleyeceğinive yönetilen bir diziyi veritabanından bir ana `SAFEARRAY`veritabanına nasıl kareşalleyeceğini gösterir.

### <a name="example"></a>Örnek

Bu örnekte, sınıf DatabaseClass ADO.NET <xref:System.Data.DataTable> bir nesne ile etkileşim için oluşturulur. Bu sınıfın yerel bir C++ `class` olduğunu unutmayın `ref class` `value class`(a veya ile karşılaştırıldığında). Bu, bu sınıfı yerel koddan kullanmak istediğimizden ve yerel kodda yönetilen türleri kullanamadığınız için gereklidir. Bu sınıf, sınıf bildiriminden önceki yönergede `#pragma managed` belirtildiği gibi CLR'yi hedeflemek üzere derlenecektir. Bu yönerge hakkında daha fazla bilgi için [yönetilen, yönetilmeyen](../preprocessor/managed-unmanaged.md)bkz.

DatabaseClass sınıfının özel üyesine `gcroot<DataTable ^> table`dikkat edin: . Yerel türler yönetilen türleri içeremediğinden, `gcroot` anahtar kelime gereklidir. Daha fazla `gcroot`bilgi için [bkz: Yerel Türlerde Tanıtıcıları Bildirin.](../dotnet/how-to-declare-handles-in-native-types.md)

Bu örnekteki kodun geri kalanı, önceki `#pragma unmanaged` `main`yönergede belirtildiği gibi yerel C++ kodudur. Bu örnekte, VeritabanıSınıfı'nın yeni bir örneğini oluşturuyoruz ve tablo oluşturmak ve tablodaki bazı satırları doldurmak için yöntemlerini çağırıyoruz. ArrayIntsCol veritabanı sütunu için değer olarak yerel `SAFEARRAY` türlerin geçirildiğini unutmayın. DatabaseClass içinde, `SAFEARRAY` bu tür <xref:System.Runtime.InteropServices?displayProperty=fullName> ad alanında bulunan mareşal işlevi kullanılarak yönetilen nesnelere marshaled. Özellikle, yöntem <xref:System.Runtime.InteropServices.Marshal.Copy%2A> bir tamsayı `SAFEARRAY` yönetilen bir dizi a mareşal <xref:System.Runtime.InteropServices.Marshal.Copy%2A> için kullanılır ve yöntem bir `SAFEARRAY`tamsayılar yönetilen bir dizi mareşal için kullanılır .

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

- Kodu komut satırından derlemek için kod örneğini adonet_marshal_safearray.cpp adlı bir dosyaya kaydedin ve aşağıdaki deyimi girin:

    ```
    cl /clr /FU System.dll /FU System.Data.dll /FU System.Xml.dll adonet_marshal_safearray.cpp
    ```

## <a name="net-framework-security"></a>.NET Framework Güvenliği

ADO.NET ilgili güvenlik sorunları hakkında bilgi için, [ADO.NET Uygulamaları Güvence Altına Alma](/dotnet/framework/data/adonet/securing-ado-net-applications)konusuna bakın.

## <a name="related-sections"></a>İlgili Bölümler

|Section|Açıklama|
|-------------|-----------------|
|[ADO.NET](/dotnet/framework/data/adonet/index)|Veri erişim hizmetlerini .NET programcısına sunan bir sınıf kümesi olan ADO.NET genel bakış sağlar.|

## <a name="see-also"></a>Ayrıca bkz.

[C++/CLI (Visual C++) ile .NET Programlama](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

[Yerel ve.NET Birlikte Çalışabilirliği](../dotnet/native-and-dotnet-interoperability.md)

<xref:System.Runtime.InteropServices>

[Birlikte Çalışabilirlik](/dotnet/framework/interop/index)
