---
title: safe_cast (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
ms.openlocfilehash: 42e141caed720aa29cf918a2bdf69d9a2c4203dc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509549"
---
# <a name="safe_cast-ccli-and-ccx"></a>safe_cast (C++/CLI ve C++/CX)

**Safe_cast** işlemi, başarılı olursa belirtilen tür olarak belirtilen ifadeyi döndürür; Aksi takdirde, `InvalidCastException`atar.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliği için tüm çalışma zamanları için uygulanan bir açıklama yoktur.)

### <a name="syntax"></a>Sözdizimi

```cpp
[default]:: safe_cast< type-id >( expression )
```

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

**safe_cast** , belirtilen bir ifadenin türünü değiştirmenize izin verir. Bir değişkenin veya parametrenin belirli bir türe dönüştürülebilir olması durumunda, geliştirme sırasında programlama hatalarını algılamak için **try-catch** bloğu olmadan **safe_cast** kullanabilirsiniz. Daha fazla bilgi için bkz. [atamaC++(/CX)](../cppcx/casting-c-cx.md).

### <a name="syntax"></a>Sözdizimi

```cpp
[default]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>Parametreler

*tür kimliği*<br/>
*İfadenin* dönüştürülecek tür. Başvuruya veya değer türüne yönelik bir tanıtıcı, bir değer türü veya bir başvuruya veya değer türüne yönelik izleme başvurusu.

*ifadesini*<br/>
Başvuruya veya değer türüne bir tanıtıcı, bir değer türü veya bir başvuruya ya da değer türüne yönelik izleme başvurusuna değerlendirilen bir ifade.

### <a name="remarks"></a>Açıklamalar

**safe_cast** , `InvalidCastException` *ifadeyi* *tür kimliği*tarafından belirtilen türe dönüştüremiyorsa atar. Yakalamak `InvalidCastException`için [/Eh (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md) derleyici seçeneğini belirtin ve bir **try/catch** ifadesini kullanın.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, Windows Çalışma Zamanı ile **safe_cast** 'in nasıl kullanılacağını gösterir.

```cpp
// safe_cast_ZW.cpp
// compile with: /ZW /EHsc

using namespace default;
using namespace Platform;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main(Array<String^>^ args) {
   I1^ i1 = ref new X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // Fails because i1 is not derived from I3.
   }
   catch(InvalidCastException^ ic) {
   wprintf(L"Caught expected exception: %s\n", ic->Message);
   }
}
```

```Output
Caught expected exception: InvalidCastException
```

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

**safe_cast** , bir ifadenin türünü değiştirmenize ve doğrulanabilir MSIL kodu oluşturmanıza olanak sağlar.

### <a name="syntax"></a>Sözdizimi

```cpp
[cli]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>Parametreler

*tür kimliği*<br/>
Başvuruya veya değer türüne yönelik bir tanıtıcı, bir değer türü veya bir başvuruya veya değer türüne yönelik izleme başvurusu.

*ifadesini*<br/>
Başvuruya veya değer türüne bir tanıtıcı, bir değer türü veya bir başvuruya ya da değer türüne yönelik izleme başvurusuna değerlendirilen bir ifade.

### <a name="remarks"></a>Açıklamalar

İfade `safe_cast<` *türü-kimliği*`>(`*ifadesi*, işlenen ifadesini tür-kimliği türünde bir nesneye dönüştürür.`)`

Derleyici çoğu yerde bir **safe_cast**kabul edeceği bir [static_cast](../cpp/static-cast-operator.md) kabul eder.  Ancak **safe_cast** , bir **STATIC_CAST** 'nin doğrulanamayan MSIL üretebildiği doğrulanabilir MSIL oluşturma garantisi vardır.  Doğrulanabilen kod hakkında daha fazla bilgi için bkz. [saf ve Doğrulanabilen kod (C++/CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) ve [PEVerify. exe (PEVerify Aracı)](/dotnet/framework/tools/peverify-exe-peverify-tool) .

**Static_cast**gibi **safe_cast** , Kullanıcı tanımlı dönüştürmeleri çağırır.

Yayınlar hakkında daha fazla bilgi için bkz. [atama işleçleri](../cpp/casting-operators.md).

**safe_cast** , **const_cast** ( **const sabitine**dönüştürme) uygulamaz.

**safe_cast** , CLI ad alanıdır.  Daha fazla bilgi için bkz. [Platform, varsayılan ve CLI ad alanları](platform-default-and-cli-namespaces-cpp-component-extensions.md) .

**Safe_cast**hakkında daha fazla bilgi için bkz.

- [/Clr (C++/CLI) Ile C stili atamalar](c-style-casts-with-clr-cpp-cli.md)

- [Nasıl yapılır: C++/CLI üzerinde safe_cast kullanma](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Derleyicinin bir **static_cast** kabul etmesinin, ancak ilişkisiz arabirim türleri arasındaki yayınlar için bir **safe_cast** olduğunu kabul edeceği bir örnek.  **Safe_cast**ile derleyici bir dönüştürme hatası yayınmayacak ve dönüştürmenin mümkün olup olmadığını görmek için çalışma zamanında bir denetim gerçekleştirecek

```cpp
// safe_cast.cpp
// compile with: /clr
using namespace System;

interface class I1 {};
interface class I2 {};
interface class I3 {};

ref class X : public I1, public I2 {};

int main() {
   I1^ i1 = gcnew X;
   I2^ i2 = safe_cast<I2^>(i1);   // OK, I1 and I2 have common type: X
   // I2^ i3 = static_cast<I2^>(i1);   C2440 use safe_cast instead
   try {
      I3^ i4 = safe_cast<I3^>(i1);   // fail at runtime, no common type
   }
   catch(InvalidCastException^) {
      Console::WriteLine("Caught expected exception");
   }
}
```

```Output
Caught expected exception
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)
