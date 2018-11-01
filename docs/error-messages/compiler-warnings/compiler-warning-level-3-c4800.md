---
title: Derleyici Uyarısı (Düzey 3) C4800
ms.date: 11/04/2016
f1_keywords:
- C4800
helpviewer_keywords:
- C4800
ms.assetid: 4f409799-a250-45ed-bb5f-657691b0d9f7
ms.openlocfilehash: 591b706249201691c7a9743d2cad082eb61e68b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636143"
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