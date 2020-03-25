---
title: Derleyici Uyarısı (düzey 4) C4431
ms.date: 11/04/2016
f1_keywords:
- C4431
helpviewer_keywords:
- C4431
ms.assetid: 58434ab6-dd8d-427b-953a-602fb7453ae6
ms.openlocfilehash: d4d803ef003f2c8367c750cf6d6aef07e4032140
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185366"
---
# <a name="compiler-warning-level-4-c4431"></a>Derleyici Uyarısı (düzey 4) C4431

tür belirticisi eksik - int varsayıldı. Not: C artık varsayılan int desteği içermiyor

Bu hata, Visual Studio 2005 için yapılan derleyici uygunluk işinin sonucu olarak oluşturulabilir: görsel C++ artık varsayılan olarak türsüz tanımlayıcılar oluşturmayacaktır. Tanımlayıcının türü açıkça belirtilmelidir.

Bu uyarı varsayılan olarak kapalıdır. Daha fazla bilgi için bkz. [Varsayılan olarak kapalı olan Derleyici uyarıları](../../preprocessor/compiler-warnings-that-are-off-by-default.md) .

## <a name="example"></a>Örnek

Aşağıdaki örnek C4431 oluşturur.

```c
// C4431.c
// compile with: /c /W4
#pragma warning(default:4431)
i;   // C4431
int i;   // OK
```
