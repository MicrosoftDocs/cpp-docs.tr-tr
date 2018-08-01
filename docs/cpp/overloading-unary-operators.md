---
title: Aşırı yükleme birli işleçleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- unary operators [C++], plus
- increment operators [C++], overloaded
- unary operators [C++], minus
- operators [C++], unary
- redefinable unary operators [C++]
- unary operators [C++]
- pointer dereference operator overloading
- plus operator
ms.assetid: 7683ef08-42a4-4283-928f-d3dd4f3ab4c0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c00f9d40fedd084afa2da6e2e7bfaf0ee831b3a9
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401886"
---
# <a name="overloading-unary-operators"></a>Aşırı Yükleme Birli İşleçleri
Aşırı yüklenebilen birli işleçler şunlardır:  
  
1.  `!` ([mantıksal değil](../cpp/logical-negation-operator-exclpt.md))  
  
2.  `&` ([adres](../cpp/address-of-operator-amp.md))  
  
3.  `~` ([birinin tamamlayıcısı](../cpp/one-s-complement-operator-tilde.md))  
  
4.  `*` ([işaretçiye](../cpp/indirection-operator-star.md))  
  
5.  `+` ([birli artı](../cpp/additive-operators-plus-and.md))  
  
6.  `-` ([tekli olumsuzlama](../cpp/additive-operators-plus-and.md))  
  
7.  `++` ([artışı](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
8.  `--` ([azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
9. dönüştürme işleçleri  
  
 Sonek artırma ve azaltma işleçleri (`++` ve `--`) içinde ayrı ayrı değerlendirilir [artırmak ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
 Dönüştürme işleçleri de ayrı bir konuda ele alınmıştır; bkz: [kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).  
  
 Aşağıdaki kurallar diğer tüm birli işleçler için doğrudur. Birli işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:  
  
 `ret-type operator` `op` `()`  
  
 Burada `ret-type` dönüş türü ve `op` yukarıdaki tabloda listelenen işleçlerden.  
  
 Birli işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:  
  
 `ret-type operator` `op` (`arg` )  
  
 Burada `ret-type` ve `op` üye işleci işlevleri için tanımlanmıştır ve `arg` üzerinde çalışacağı sınıf türünün bir bağımsız değişken.  
  
> [!NOTE]
>  Birli operatörlerin dönüş türleriyle ilgili bir kısıtlama yoktur. Örneğin, mantıksal değil için mantıklıdır (`!`) bir tamsayı değeri, ancak bu döndürülecek zorlanmaz.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)