---
title: statik depolama sınıfı tanımlayıcısı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8a7d61e39eb706721ddf936f88f5df02a6eddf96
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı
Bir değişken bildirilen iç düzeyindeki **statik** depolama sınıfı tanımlayıcısı genel ömrü ancak yalnızca blokta görünür, bildirildiği içinde. Kullanarak sabit dizeleri için **statik** yararlıdır çünkü genellikle adlı işlevlerinde sık başlatma ek yükünü azaltır.  
  
## <a name="remarks"></a>Açıklamalar  
Açıkça başlatılamadı, bir **statik** değişken, onu 0 olarak varsayılan olarak başlatılır. Bir işlev içinde **statik** ayrılacak depolama neden olur ve bir tanımı olarak görev yapar. İç statik değişkenler yalnızca tek bir işlev için görünür özel, kalıcı depolama sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C Depolama Sınıfları](c-storage-classes.md)  
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)  