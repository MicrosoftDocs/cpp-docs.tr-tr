---
title: Derleyici hatası C2099
ms.date: 11/04/2016
f1_keywords:
- C2099
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
ms.openlocfilehash: e9fb7739111d13a585579455ed97cecaca3266e4
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/20/2019
ms.locfileid: "75301944"
---
# <a name="compiler-error-c2099"></a>Derleyici hatası C2099

Başlatıcı bir sabit değil

Bu hata yalnızca C derleyicisi tarafından verilir ve yalnızca otomatik olmayan değişkenler için gerçekleşir.  Derleyici, programın başlangıcında otomatik olmayan değişkenleri başlatır ve birlikte başlatıldığı değerler sabit olmalıdır.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2099 oluşturur.

```c
// C2099.c
int j;
int *p;
j = *p;   // C2099 *p is not a constant
```

## <a name="example"></a>Örnek

C2099, kayan nokta duyarlık ortam ayarları (daha fazla bilgi için [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) bakın), çalışma zamanına göre derlemeden farklı olabileceğinden, derleyici **/FP: Strict** altındaki bir ifadede sabit katlama gerçekleştiremediği için de oluşabilir.

Sabit katlama başarısız olduğunda, derleyici, C 'de izin verilmeyen dinamik başlatmayı çağırır.

Bu hatayı çözmek için, modülü bir. cpp dosyası olarak derleyin veya ifadeyi kolaylaştırın.

Daha fazla bilgi için bkz. [/FP (kayan nokta davranışını belirt)](../../build/reference/fp-specify-floating-point-behavior.md).

Aşağıdaki örnek C2099 oluşturur.

```c
// C2099_2.c
// compile with: /fp:strict /c
float X = 2.0 - 1.0;   // C2099
float X2 = 1.0;   // OK
```
