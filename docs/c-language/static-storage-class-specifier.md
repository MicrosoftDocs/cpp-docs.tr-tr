---
title: static Depolama Sınıfı Tanımlayıcısı
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: e84e2745c6077f038f47295119936a1ad6431bdd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229499"
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı

Depolama sınıfı belirticisine sahip iç düzeyde tanımlanmış bir değişken **`static`** küresel bir yaşam süresine sahiptir ancak yalnızca bildirildiği blok içinde görünür. Sabit dizeler için kullanımı, **`static`** genellikle çağrılan işlevlerde sık başlatma yükünü konuma almayı azaltır için yararlıdır.

## <a name="remarks"></a>Açıklamalar

Bir değişkeni açıkça başlatmadıysanız **`static`** Varsayılan olarak 0 olarak başlatılır. Bir işlevin içinde, **`static`** depolamanın ayrılmasına ve bir tanım olarak hizmet vermesine neden olur. İç statik değişkenler, özel ve kalıcı depolamayı yalnızca tek bir işleve görünür hale sunar.

## <a name="see-also"></a>Ayrıca bkz.

[C Depolama sınıfları](c-storage-classes.md)<br/>
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)
