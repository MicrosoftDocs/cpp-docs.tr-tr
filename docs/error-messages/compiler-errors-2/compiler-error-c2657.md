---
title: Derleyici Hatası C2657 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2657
dev_langs:
- C++
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 342b336582b7920756a17b99f0d52dcb28c7173a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46109983"
---
# <a name="compiler-error-c2657"></a>Derleyici Hatası C2657

' sınıf:: *' deyiminin başlangıcında bulunamadı (bir tür belirtmeyi unuttunuz mu?)

Satır bir işaretçi-üye tanımlayıcısı başladı.

Bu hata bir işaretçinin bildiriminde tür belirticisi eksik bir üyesine neden olabilir.

Aşağıdaki örnek, C2657 oluşturur:

```
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```