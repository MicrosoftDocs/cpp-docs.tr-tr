---
title: Çalışma zamanı türü bilgileri | Microsoft Docs
ms.custom: index-page
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- RTTI compiler option
- run-time type information
- run time, type checking
- type information, run-time type checking
- run-time checks, type checking
ms.assetid: becbd0e5-0439-4c61-854f-8a74f7160c54
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1244c05b7af94d69394c412a3c67864d6e75c337
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46050885"
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