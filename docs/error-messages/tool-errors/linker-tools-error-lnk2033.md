---
title: Bağlayıcı araçları hatası LNK2033 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2033
dev_langs:
- C++
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6c547b4d35e2e7fe057cdd67f0dad47f58d000c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46040004"
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