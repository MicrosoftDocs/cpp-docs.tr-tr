---
title: Çalışma Zamanı Türü Bilgileri
ms.custom: index-page
ms.date: 11/04/2016
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
ms.openlocfilehash: 1d11ee3ea472f935120c59f0faefee905361ee97
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62267408"
---
# <a name="run-time-type-information"></a>Çalışma Zamanı Türü Bilgileri

Çalışma zamanı tür bilgisini (RTTI) program yürütme sırasında belirlenmesi için bir nesne türünü izin veren mekanizmadır. Sınıf kitaplıklarının birçok satıcı bu işlevselliği kendilerini uygulama çünkü RTTI C++ dil eklendi. Bu kitaplıklar arasında uyumsuzluk nedeniyle. Bu nedenle, belirgin hale için dil düzeyinde gerekli bir çalışma zamanı türü bilgileri destekler.

Netlik sağlamak, bu tartışma RTTI işaretçileri neredeyse tamamen büyük/küçük harf sınırlıdır. Bununla birlikte, açıklanan kavramları başvurular için de geçerlidir.

Çalışma zamanı türü bilgileri için üç ana C++ dil öğeleri şunlardır:

- [Dynamic_cast](../cpp/dynamic-cast-operator.md) işleci.

   Çok biçimli türlerin dönüştürülmesi için kullanılır.

- [TypeID](../cpp/typeid-operator.md) işleci.

   Bir nesnenin tam tür tanımlamak için kullanılır.

- [Type_info](../cpp/type-info-class.md) sınıfı.

   Tarafından döndürülen tür bilgileri tutmak için kullanılan **TypeID** işleci.

## <a name="see-also"></a>Ayrıca bkz.

[Atama](../cpp/casting.md)