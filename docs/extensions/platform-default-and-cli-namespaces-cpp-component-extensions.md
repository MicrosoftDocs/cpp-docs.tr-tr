---
title: Platform, varsayılan ve cli ad alanları (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- lang
- cli
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
ms.openlocfilehash: a7599e2987d27626e6f5c9d049d9a3bd4509c3ff
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59028515"
---
# <a name="platform-default-and-cli-namespaces--ccli-and-ccx"></a>Platform, varsayılan ve cli ad alanları (C++/CLI ve C++/CX)

Bir ad alanı dil öğelerinin adlarını kaynak kod içindeki başka bir yerde benzer adlarla çakışmamaları için örtük olarak nitelendirir. Bir ad çakışması derleyicinin tanımasını gibi engelleyebilir [Context-Sensitive Keywords](context-sensitive-keywords-cpp-component-extensions.md). Ad alanları derleyici tarafından kullanılır, ancak oluşturulmuş derlemede korunmaz.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Proje oluşturduğunuzda, visual Studio projeniz için varsayılan ad alanı sağlar. El ile ad alanı C + rağmen yeniden adlandırabilirsiniz +/ CX .winmd dosyasının adı kök ad alanının adı eşleşmelidir.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için [ad alanları ve tür görünürlüğü (C++/CX)](https://msdn.microsoft.com/library/windows/apps/hh969551.aspx).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
using namespace cli;
```

### <a name="remarks"></a>Açıklamalar

C++/CLI destekler **CLI** ad alanı. İle derlerken `/clr`, **kullanarak** sözdizimi bölümündeki deyimi kastedilir.

Aşağıdaki dil özellikleri **CLI** ad alanı:

- [Diziler](arrays-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)

- [pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)

- [safe_cast](safe-cast-cpp-component-extensions.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, sembol kullanmak mümkün olduğunu gösterir **CLI** kodunuzda kullanıcı tanımlı bir sembol olarak ad alanı.  Ancak, bunu yaptıktan sonra açıkça veya örtük olarak nitelendirmeniz gerekecek **CLI** dil öğesinde aynı ada sahip.

```cpp
// cli_namespace.cpp
// compile with: /clr
using namespace cli;
int main() {
   array<int> ^ MyArray = gcnew array<int>(100);
   int array = 0;

   array<int> ^ MyArray2 = gcnew array<int>(100);   // C2062

   // OK
   cli::array<int> ^ MyArray2 = gcnew cli::array<int>(100);
   ::array<int> ^ MyArray3 = gcnew ::array<int>(100);
}
```

## <a name="see-also"></a>Ayrıca bkz.

[.NET ve UWP İçin Bileşen Uzantıları](component-extensions-for-runtime-platforms.md)