---
title: "statik depolama sınıfı tanımlayıcısı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- static variables, specifier
- storage classes, static
- static storage class specifiers
ms.assetid: 9bce361e-919b-46b9-8148-40d7ab0eb024
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a51dfc10ac0ae05a67a280b4b76c2c92eb57a0b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı
Bir değişken bildirilen iç düzeyindeki **statik** depolama sınıfı tanımlayıcısı genel ömrü ancak yalnızca blokta görünür, bildirildiği içinde. Kullanarak sabit dizeleri için **statik** yararlıdır çünkü genellikle adlı işlevlerinde sık başlatma ek yükünü azaltır.  
  
## <a name="remarks"></a>Açıklamalar  
Açıkça başlatılamadı, bir **statik** değişken, onu 0 olarak varsayılan olarak başlatılır. Bir işlev içinde **statik** ayrılacak depolama neden olur ve bir tanımı olarak görev yapar. İç statik değişkenler yalnızca tek bir işlev için görünür özel, kalıcı depolama sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C depolama sınıfları](c-storage-classes.md)  
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)  