---
title: safe_cast (C + +/ CLI ve C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- safe_cast
- safe_cast_cpp
- stdcli::language::safe_cast
dev_langs:
- C++
helpviewer_keywords:
- safe_cast keyword [C++]
ms.assetid: 4fa688bf-a8ec-49bc-a4c5-f48134efa4f7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2b8f9b1e40deadbc23fe19f02bf2aaef899c52a6
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50056703"
---
# <a name="safecast-ccli-and-ccx"></a>safe_cast (C + +/ CLI ve C + +/ CX)

**Safe_cast** işlemi başarılı olursa, belirtilen tür olarak belirtilen bir ifade döndürür; Aksi durumda `InvalidCastException`.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

(Bu dil özelliğinin tüm çalışma zamanları için geçerli olan açıklaması yoktur.)

### <a name="syntax"></a>Sözdizimi

```cpp
[default]:: safe_cast< type-id >( expression )
```

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

**safe_cast** belirtilen ifade türünü değiştirmenize izin verir. Burada tam beklediğiniz bir değişken veya parametre belirli bir türe dönüştürülebilir durumlarda, kullandığınız **safe_cast** olmadan bir **try-catch** geliştirme sırasında programlama hatalarını algılamak için blok. Daha fazla bilgi için [atama (C + +/ CX)](https://msdn.microsoft.com/library/windows/apps/hh755802.aspx).

### <a name="syntax"></a>Sözdizimi

```cpp
[default]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>Parametreler

*tür kimliği*<br/>
Dönüştürme türü *ifade* için. Bir başvuru veya değer türü, bir değer türü veya başvuru veya değer türüne yönelik izleme başvurusuna yönelik bir tanıtıcı.

*İfade*<br/>
Bir başvuru veya değer türü, bir değer türü veya başvuru veya değer türüne yönelik izleme başvurusuna yönelik bir tanıtıcı için değerlendirilen bir ifade.

### <a name="remarks"></a>Açıklamalar

**safe_cast** oluşturur `InvalidCastException` bunu dönüştüremezse *ifade* tarafından belirtilen türe *türü kimliği*. Yakalamak için `InvalidCastException`, belirtin [/EH (özel durum işleme modeli)](../build/reference/eh-exception-handling-model.md) derleyici seçeneği ve kullanım bir **try/catch** deyimi.

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneğinde nasıl kullanılacağını gösterir **safe_cast** Windows çalışma zamanı ile.

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

**safe_cast** bir ifade türünü değiştirin ve doğrulanabilir MSIL kodu oluştur olanak tanır.

### <a name="syntax"></a>Sözdizimi

```cpp
[cli]:: safe_cast< type-id >( expression )
```

### <a name="parameters"></a>Parametreler

*tür kimliği*<br/>
Bir başvuru veya değer türü, bir değer türü veya başvuru veya değer türüne yönelik izleme başvurusuna yönelik bir tanıtıcı.

*İfade*<br/>
Bir başvuru veya değer türü, bir değer türü veya başvuru veya değer türüne yönelik izleme başvurusuna yönelik bir tanıtıcı için değerlendirilen bir ifade.

### <a name="remarks"></a>Açıklamalar

İfade `safe_cast<` *türü kimliği*`>(`*ifade* `)` işlenen dönüştürür *ifade* türündebirnesneiçin*türü kimliği*.

Derleyici kabul edileceği bir [static_cast](../cpp/static-cast-operator.md) kabul eder, birçok yerde bir **safe_cast**.  Ancak, **safe_cast** doğrulanabilir MSIL oluşturmak için garantili oysa bir **static_cast** doğrulanamayan MSIL'yi üretebilir.  Bkz: [saf ve doğrulanabilen kod (C + +/ CLI)](../dotnet/pure-and-verifiable-code-cpp-cli.md) ve [Peverify.exe (PEVerify aracı)](/dotnet/framework/tools/peverify-exe-peverify-tool) doğrulanabilen kod hakkında daha fazla bilgi için.

Gibi **static_cast**, **safe_cast** kullanıcı tanımlı dönüşümler çağırır.

Atamaları hakkında daha fazla bilgi için bkz: [atama işleçleri](../cpp/casting-operators.md).

**safe_cast** uygulanmaz bir **const_cast** (hemen cast **const**).

**safe_cast** CLI ad alanındadır.  Bkz: [Platform, varsayılan ve cli ad alanları](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md) daha fazla bilgi için.

Daha fazla bilgi için **safe_cast**, bkz:

- [/ CLR ile C türü atamalar (C + +/ CLI)](../windows/c-style-casts-with-clr-cpp-cli.md)

- [Nasıl yapılır: C++/CLI üzerinde safe_cast kullanma](../dotnet/how-to-use-safe-cast-in-cpp-cli.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Bir örneği burada derleyici kabul bir **static_cast** kabul eder, ancak bir **safe_cast** ilgisiz arabirim türleri arasında yayınları içindir.  İle **safe_cast**, derleyici bir dönüştürme hatası veremez ve dönüştürme mümkün olup olmadığını görmek için çalışma zamanında bir denetimi gerçekleştirir

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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP İçin Bileşen Uzantıları](../windows/component-extensions-for-runtime-platforms.md)
