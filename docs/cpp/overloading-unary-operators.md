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
ms.openlocfilehash: d7f242fac0d81c6d46c2d810bf07459fde2fb2ae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="overloading-unary-operators"></a>Aşırı Yükleme Birli İşleçleri
Aşırı yüklenebilen birli işleçler şunlardır:  
  
1.  `!` ([mantıksal değil](../cpp/logical-negation-operator-exclpt.md))  
  
2.  `&` ([adres,](../cpp/address-of-operator-amp.md))  
  
3.  `~` ([birinin tamamlama](../cpp/one-s-complement-operator-tilde.md))  
  
4.  `*` ([işaretçiye](../cpp/indirection-operator-star.md))  
  
5.  `+` ([birli artı](../cpp/additive-operators-plus-and.md))  
  
6.  `-` ([tekli değilleme](../cpp/additive-operators-plus-and.md))  
  
7.  `++` ([artırma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
8.  `--` ([azaltma](../cpp/prefix-increment-and-decrement-operators-increment-and-decrement.md))  
  
9. dönüştürme işleçleri  
  
 Sonek arttırma ve azaltma işleçleri (`++` ve **--**) üzerinde ayrı olarak davranılır [artırmak ve azaltma](../cpp/increment-and-decrement-operator-overloading-cpp.md).  
  
 Dönüştürme işleçleri ayrıca ayrı bir konuda ele alınmıştır; bkz: [kullanıcı tanımlı tür dönüşümleri](../cpp/user-defined-type-conversions-cpp.md).  
  
 Aşağıdaki kurallar diğer tüm birli işleçler için doğrudur. Birli işleç işlevini statik olmayan bir üye olarak bildirmek için şu biçimde bildirmeniz gerekir:  
  
 `ret-type operator` `op` `()`  
  
 Burada `ret-type` dönüş türü ve `op` yukarıdaki tabloda listelenen işleçleri birinin.  
  
 Birli işleç işlevini genel bir işlev olarak bildirmek için şu biçimde bildirmeniz gerekir:  
  
 `ret-type operator` `op` (`arg` )  
  
 Burada `ret-type` ve `op` üye işleci işlevleri için açıklanan ve `arg` üzerinde çalışılacak sınıfı türünde bir bağımsız değişken değil.  
  
> [!NOTE]
>  Birli operatörlerin dönüş türleriyle ilgili bir kısıtlama yoktur. Örneğin, mantıksal değil için mantıklıdır (`!`) bir tamsayı değeri, ancak bu döndürülecek zorunlu tutulmaz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İşleç Aşırı Yüklemesi](../cpp/operator-overloading.md)