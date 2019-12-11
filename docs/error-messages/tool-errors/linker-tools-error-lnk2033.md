---
title: Bağlayıcı Araçları Hatası LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 407f5eaf94a0e2da43425c3bbdd1955a88c95f14
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991181"
---
# <a name="linker-tools-error-lnk2033"></a>Bağlayıcı Araçları Hatası LNK2033

çözümlenmemiş TypeRef belirteci (belirteç) ' Type ' için

Bir türün MSIL meta verilerinde bir tanımı yok.

**/Clr: Safe** Ile derlerken LNK2033 ve bir MSIL modülünde tür için yalnızca bir iletme bildirimi olduğunda, bu tür MSIL modülünde başvuruluyorsa meydana gelebilir.

Türün **/clr: Safe**altında tanımlanması gerekir.

Daha fazla bilgi için bkz. [/clr (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek LNK2033 oluşturur.

```cpp
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```
