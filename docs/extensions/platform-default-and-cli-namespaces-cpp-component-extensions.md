---
title: Platform, Default ve CLI ad alanları (C++/CLI ve C++/CX)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- lang
- cli
helpviewer_keywords:
- lang namespace
- cli namespace
ms.assetid: 9d38bd1e-dc78-47d1-a84b-9b4683e52c9c
ms.openlocfilehash: db6c73d6c52bf97aea5d0fbeeeebdeef87f692cc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509762"
---
# <a name="platform-default-and-cli-namespaces--ccli-and-ccx"></a>Platform, Default ve CLI ad alanları (C++/CLI ve C++/CX)

Bir ad alanı dil öğelerinin adlarını kaynak kod içindeki başka bir yerde benzer adlarla çakışmamaları için örtük olarak nitelendirir. Örneğin, bir ad çakışması derleyicinin [bağlama duyarlı anahtar sözcükleri](context-sensitive-keywords-cpp-component-extensions.md)tanımasını engelleyebilir. Ad alanları derleyici tarafından kullanılır, ancak oluşturulmuş derlemede korunmaz.

## <a name="all-runtimes"></a>Tüm Çalışma Zamanları

Projeyi oluştururken, Visual Studio projeniz için varsayılan bir ad alanı sağlar. Ad alanını el ile yeniden adlandırabilirsiniz, ancak/CX C++içinde. winmd dosyasının adı kök ad alanının adıyla aynı olmalıdır.

## <a name="windows-runtime"></a>Windows Çalışma Zamanı

Daha fazla bilgi için bkz. [ad alanları ve türC++görünürlüğü (/CX)](../cppcx/namespaces-and-type-visibility-c-cx.md).

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/ZW`

## <a name="common-language-runtime"></a>Ortak Dil Çalışma Zamanı

### <a name="syntax"></a>Sözdizimi

```cpp
using namespace cli;
```

### <a name="remarks"></a>Açıklamalar

C++/CLI, **CLI** ad alanını destekler. İle `/clr`derlerken, söz dizimi bölümünde **using** deyimleri kapsanır.

Aşağıdaki dil özellikleri **CLI** ad alanında bulunur:

- [Diziler](arrays-cpp-component-extensions.md)

- [interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)

- [pin_ptr (C++/CLI)](pin-ptr-cpp-cli.md)

- [safe_cast](safe-cast-cpp-component-extensions.md)

### <a name="requirements"></a>Gereksinimler

Derleyici seçeneği:`/clr`

### <a name="examples"></a>Örnekler

Aşağıdaki kod örneği, kodunuzda Kullanıcı tanımlı bir sembol olarak **CLI** ad alanında bir sembol kullanmanın mümkün olduğunu gösterir.  Ancak, bu işlemi tamamladıktan sonra aynı ada sahip **CLI** dili öğesi için başvurularınızı açıkça veya örtük olarak nitelemeniz gerekir.

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