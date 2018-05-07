---
title: Kaynak Derleyicisi uyarısı RW4004 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RW4004
dev_langs:
- C++
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 94bd1c043ac5660c5cb8fc8b2bfa1dd2f6968b55
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="resource-compiler-warning-rw4004"></a>Kaynak Derleyicisi Uyarısı RW4004
ASCII karakter sanal anahtar kodu eşdeğer değil  
  
 Bir dize sabit değeri VIRTKEY Türü Hızlandırıcı sanal anahtar kodunu kullanıldı.  
  
 Bu uyarı, devam ancak oluşturulan Hızlandırıcı tuşları belirttiğiniz dizesi eşleşmeyebilir unutmayın olanak sağlar. (VIRTKEYs ASCII Hızlandırıcıları daha farklı anahtar kodları kullanın.)  
  
 Dize değişmez değerleri sözdizimsel olarak geçerli durumdayken, yalnızca kullanarak istediğiniz Hızlandırıcı alma sağlayabilirsiniz **VK_\* #define** WINDOWS.h değerleri.