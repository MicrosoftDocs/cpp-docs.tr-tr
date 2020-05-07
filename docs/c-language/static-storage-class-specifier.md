---
title: static Depolama Sınıfı Tanımlayıcısı
ms.date: 11/04/2016
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
ms.openlocfilehash: ef85ee4d757cb9579431427fba7b46a0e5ac905f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157948"
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı

**Statik** depolama sınıfı belirticisine sahip iç düzeyde tanımlanmış bir değişken, genel bir yaşam süresine sahiptir ancak yalnızca bildirildiği blok içinde görünür. Sabit dizeler için, genellikle çağrılan işlevlerde sık başlatma yükünü konuma almayı azaltır için **statik** kullanmak faydalıdır.

## <a name="remarks"></a>Açıklamalar

**Statik** bir değişkeni açıkça atamadıysanız varsayılan olarak 0 olarak başlatılır. Bir işlevin içinde, **statik** depolamanın ayrılmasına ve bir tanım olarak hizmet vermesine neden olur. İç statik değişkenler, özel ve kalıcı depolamayı yalnızca tek bir işleve görünür hale sunar.

## <a name="see-also"></a>Ayrıca bkz.

[C Depolama Sınıfları](c-storage-classes.md)<br/>
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)
