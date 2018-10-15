---
title: Platform, varsayılan ve cli ad alanları (C + +/ CLI ve C + +/ CX) | Microsoft Docs
ms.custom: ''
ms.date: 10/12/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- lang
- cli
dev_langs:
- C++
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a70fb5317f42e98ccddb21fe66e328e1cc6f7643
ms.sourcegitcommit: 3f4e92266737ecb70507871e87dc8e2965ad7e04
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/15/2018
ms.locfileid: "49328031"
---
# <a name="platform-default-and-cli-namespaces--ccli-and-ccx"></a>Platform, varsayılan ve cli ad alanları (C + +/ CLI ve C + +/ CX)

Bir ad alanı dil öğelerinin adlarını kaynak kod içindeki başka bir yerde benzer adlarla çakışmamaları için örtük olarak nitelendirir. Bir ad çakışması derleyicinin tanımasını gibi engelleyebilir [Context-Sensitive Keywords](../windows/context-sensitive-keywords-cpp-component-extensions.md). Ad alanları derleyici tarafından kullanılır, ancak oluşturulmuş derlemede korunmaz.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Proje oluşturduğunuzda, visual Studio projeniz için varsayılan ad alanı sağlar. El ile ad alanı C + rağmen yeniden adlandırabilirsiniz +/ CX .winmd dosyasının adı kök ad alanının adı eşleşmelidir.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için [ad alanları ve tür görünürlüğü (C + +/ CX)](https://msdn.microsoft.com/library/windows/apps/hh969551.aspx).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği: `/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
using namespace cli;
```

### <a name="remarks"></a>Açıklamalar

C + +/ CLI destekler **CLI** ad alanı. İle derlerken `/clr`, **kullanarak** sözdizimi bölümündeki deyimi kastedilir.

Aşağıdaki dil özellikleri **CLI** ad alanı:

- [Diziler](../windows/arrays-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](../windows/interior-ptr-cpp-cli.md)

- [pin_ptr (C++/CLI)](../windows/pin-ptr-cpp-cli.md)

- [safe_cast](../windows/safe-cast-cpp-component-extensions.md)

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

## <a name="see-also"></a>Ayrıca Bkz.

[.NET ve UWP için bileşen uzantıları](../windows/component-extensions-for-runtime-platforms.md)