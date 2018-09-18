---
title: Derleyici Hatası C2099 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2099
dev_langs:
- C++
helpviewer_keywords:
- C2099
ms.assetid: 30e151ee-d458-4901-b0c0-d45054a913f5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8fcbefa4d8fb9d5503f28cf3bf39cafc6b05a225
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116834"
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