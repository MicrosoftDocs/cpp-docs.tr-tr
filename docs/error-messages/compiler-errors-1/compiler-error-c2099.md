---
title: Derleyici Hatası C2099
ms.date: 11/04/2016
f1_keywords:
- C2099
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
ms.openlocfilehash: 9c83b4a50cb9cf5c5b1992f0f64e2eeb013b48e4
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376948"
---
# <a name="compiler-error-c2099"></a>Derleyici Hatası C2099

Başlatıcı bir sabit değil

Bu hata yalnızca C derleyicisi tarafından verilir ve yalnızca otomatik olmayan değişkenleri için gerçekleşir.  Derleyici program başlangıcında otomatik olmayan değişkenleri başlatır ve ile başlatılmış değerlerin sabit olması gerekir.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2099 oluşturur.

```
// C2099.c
int j;
int *p;
j = *p;   // C2099 *p is not a constant
```

## <a name="example"></a>Örnek

C2099 arasındaki derleyici sabit bir ifade altında katlamalarını gerçekleştirmek mümkün olmadığından da gerçekleşebilir **/FP: strict** kayan nokta çünkü duyarlık ortam ayarları (bkz [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md) için Daha fazla bilgi), çalışma zamanı için derleme farklı olabilir.

Sabit zaman başarısız Katlama, derleyici, C'de izin verilmeyen dinamik başlatma çağırır.

Bu hatayı gidermek için modül bir .cpp dosyası olarak derleyin veya ifadeyi basitleştirin.

Daha fazla bilgi için [FP (Floating-Point davranışını belirtin)](../../build/reference/fp-specify-floating-point-behavior.md).

Aşağıdaki örnek, C2099 oluşturur.

```
// C2099_2.c
// compile with: /fp:strict /c
float X = 2.0 - 1.0;   // C2099
float X2 = 1.0;   // OK
```