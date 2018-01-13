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
ms.workload: cplusplus
ms.openlocfilehash: c957b78eeb506e9f1f91a670cf5cc4d52ad72878
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="static-storage-class-specifier"></a>static Depolama Sınıfı Tanımlayıcısı
Bir değişken bildirilen iç düzeyindeki **statik** depolama sınıfı tanımlayıcısı genel ömrü ancak yalnızca blokta görünür, bildirildiği içinde. Kullanarak sabit dizeleri için **statik** yararlıdır çünkü genellikle adlı işlevlerinde sık başlatma ek yükünü azaltır.  
  
## <a name="remarks"></a>Açıklamalar  
Açıkça başlatılamadı, bir **statik** değişken, onu 0 olarak varsayılan olarak başlatılır. Bir işlev içinde **statik** ayrılacak depolama neden olur ve bir tanımı olarak görev yapar. İç statik değişkenler yalnızca tek bir işlev için görünür özel, kalıcı depolama sağlar.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
[C Depolama Sınıfları](c-storage-classes.md)  
[Depolama sınıfları (C++)](../cpp/storage-classes-cpp.md)  