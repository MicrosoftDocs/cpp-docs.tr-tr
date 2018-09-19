---
title: Derleyici Uyarısı (Düzey 3) C4800 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4800
dev_langs:
- C++
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b5a19c27731192a5fe2930aec3e78fb66d790484
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46090914"
---
# <a name="compiler-warning-level-3-c4800"></a>Derleyici Uyarısı (Düzey 3) C4800

> '*türü*': değer bool 'true' veya 'false' (Performans Uyarısı) zorlama

Bir değeri, olmadığında bu uyarı oluşturulur `bool` atanmış veya türe durumunda bırakılması `bool`. Atayarak bu ileti genellikle, kaynaklanır `int` değişkenlere `bool` değişkenleri burada `int` değişkeni yalnızca verileri içeren **true** ve **false**ve olabilir tür olarak yeniden tanımlanıyor `bool`. İfadeyi türü yeniden yazma, `bool`, ekleyebileceğiniz sonra "`!=0`" ifade, ifade türü sağlayan `bool`. İfade türüne atama `bool` bilinçli olarak böyle tasarlanmıştır uyarı devre dışı bırakmaz.

Bu uyarı artık Visual Studio 2017'de oluşturulur.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C4800 oluşturur ve bu sorunun nasıl gösterir:

```cpp
// C4800.cpp
// compile with: /W3
int main() {
   int i = 0;

   // To fix, instead try:
   // bool i = 0;

   bool j = i;   // C4800
   j++;
}
```