---
title: Bağlayıcı Araçları Hatası LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 7e95823e23215848ff3e5d201171523c9009eb2d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62298912"
---
# <a name="linker-tools-error-lnk2033"></a>Bağlayıcı Araçları Hatası LNK2033

'type' için typeref belirteci (belirteç)

Bir tür tanımı MSIL meta verilerde yok.

İle derlerken LNK2033 oluşabilir **/CLR: safe** ve burada yalnızca ileri dönük bildiriminin bir türü burada türü başvuruluyor MSIL modülünde bir MSIL modülü için.

Türü altında tanımlanmış olması gereken **/CLR: safe**.

Daha fazla bilgi için [/CLR (ortak dil çalışma zamanı derlemesi)](../../build/reference/clr-common-language-runtime-compilation.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, LNK2033 oluşturur.

```
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