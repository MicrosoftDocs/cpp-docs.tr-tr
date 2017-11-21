---
title: "Kaynak Derleyicisi uyarısı RW4004 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW4004
dev_langs: C++
helpviewer_keywords: RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: aedc73ddc2934cf44ae5ebf98cf0e4e50814feb9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-warning-rw4004"></a>Kaynak Derleyicisi Uyarısı RW4004
ASCII karakter sanal anahtar kodu eşdeğer değil  
  
 Bir dize sabit değeri VIRTKEY Türü Hızlandırıcı sanal anahtar kodunu kullanıldı.  
  
 Bu uyarı, devam ancak oluşturulan Hızlandırıcı tuşları belirttiğiniz dizesi eşleşmeyebilir unutmayın olanak sağlar. (VIRTKEYs ASCII Hızlandırıcıları daha farklı anahtar kodları kullanın.)  
  
 Dize değişmez değerleri sözdizimsel olarak geçerli durumdayken, yalnızca kullanarak istediğiniz Hızlandırıcı alma sağlayabilirsiniz **VK_\* #define** WINDOWS.h değerleri.