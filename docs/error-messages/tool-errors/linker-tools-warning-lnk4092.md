---
title: "Bağlayıcı araçları uyarısı LNK4092 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4092
dev_langs: C++
helpviewer_keywords: LNK4092
ms.assetid: d569ec47-a338-40e1-940b-8a8061459acb
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3771cfc08a091a796e67e8c11a16c842e6a4346a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-warning-lnk4092"></a>Bağlayıcı Araçları Uyarısı LNK4092
Paylaşılan yazılabilir Bölümü 'bölüm' relocatıons içerir. Görüntü düzgün çalışmayabilir  
  
 Olası ciddi bir sorun, sizi uyaracak şekilde paylaşılan bir bölüm sahip olduğunda bu uyarı bağlayıcı yayar.  
  
 Birden çok işlem arasında veri paylaşımı için bir bölüm "paylaşılan" olarak işaretlemek için yoludur Ancak, bir bölüm paylaşılan olarak işaretleme sorunlara neden olabilir. Örneğin, paylaşılan veri bölümü şöyle bildirimlerinde içeren DLL vardır:  
  
```  
int var = 1;  
int *pvar = &var;  
```  
  
 Bağlayıcı çözümlenemiyor `pvar` burada bellekte DLL yüklü değerini bağımlı olduğundan, bu nedenle, koyar yeniden konumlandırma kayıt DLL'de. DLL adresini belleğe yüklendiği zaman `var` çözülebilir ve `pvar` atanmış. Başka bir işlem aynı DLL'yi yükler, ancak aynı anda yüklenemiyor adres, adresi için yeniden konumlandırma `var` ikinci işlemi ve ilk işlemin adres alanı yanlış adresine işaret edecek için güncelleştirilir.