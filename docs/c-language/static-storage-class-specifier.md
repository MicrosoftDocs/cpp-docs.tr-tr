---
title: static Depolama Sınıfı Tanımlayıcısı
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: 2596e257ae6e22e207451b97b0361aecdfffba03
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50594044"
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı

İç düzeydeki ile bildirilen bir değişken **statik** depolama sınıfı tanımlayıcısı genel bir ömre sahiptir, ancak yalnızca blok içinde görülebilir içinde bildirildiği. Kullanarak sabit dizeleri için **statik** sık sık çağrılan işlevlerin başlatmada ek yükü azaltır çünkü yararlıdır.

## <a name="remarks"></a>Açıklamalar

Açıkça başlatılamadı, bir **statik** değişken, 0 için varsayılan olarak başlatılır. Bir işlev içinde **statik** ayrılacak depolama neden olur ve bir tanımı görev yapar. İç statik değişkenler yalnızca tek bir işleve görünür özel, kalıcı depolama sağlar.

## <a name="see-also"></a>Ayrıca Bkz.

[C Depolama Sınıfları](c-storage-classes.md)<br/>
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)