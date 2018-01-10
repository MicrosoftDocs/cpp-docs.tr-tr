---
title: "Bağlayıcı araçları uyarısı LNK4221 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4221
dev_langs: C++
helpviewer_keywords: LNK4221
ms.assetid: 8e2eb2de-9532-4b85-908a-8c9ff5c4cccb
caps.latest.revision: "12"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3fb348ebb05b7af40821b4f3968a920c2e9e773
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4221"></a>Bağlayıcı Araçları Uyarısı LNK4221
Bu kitaplığı kullanan herhangi bir bağlantı işlem tarafından kullanılmayacak şekilde bu nesne dosyasını önceden tanımlı hiçbir ortak simgeleri tanımlamıyor  
  
 Aşağıdaki iki kod parçacıkları göz önünde bulundurun.  
  
```  
// a.cpp  
#include <atlbase.h>  
```  
  
```  
// b.cpp  
#include <atlbase.h>  
int function()  
{  
   return 0;  
}  
  
```  
  
 Dosyaları derlemek ve iki nesne dosyaları oluşturmak için Çalıştır **cl /c a.cpp b.cpp** bir komut isteminde. Nesne dosyaları çalıştırarak bağlarsanız **bağlantı//out:test.lib a.obj b.obj lib**, LNK4221 uyarı alırsınız. Çalıştırarak nesneleri bağlarsanız **bağlantı//out:test.lib b.obj a.obj lib**, bir uyarı alırsınız.  
  
 Bağlayıcı bir son giren ilk çıkar (LIFO) şekilde çalıştığından İkinci senaryoda herhangi bir uyarı verilir. İlk senaryoda b.obj a.obj önce işlenir ve a.obj eklemek için yeni simge vardır. A.obj ilk işlemek için bağlayıcı yönlendirerek uyarı önleyebilirsiniz.  
  
 İki kaynak dosyaları seçeneğini belirttiğinizde bir ortak bu hatanın nedeni [/Yc (önceden derlenmiş üst bilgi dosyası oluştur)](../../build/reference/yc-create-precompiled-header-file.md) belirtilen üstbilgi dosyası adı ile **önceden derlenmiş üstbilgi** alan. Varsayılan olarak stdafx.cpp stdafx.h içerir, yeni semboller eklemez olduğundan, bu sorunun temel nedeni stdafx.h ile ilgilidir. Başka bir kaynak dosyası ile stdafx.h içeriyorsa **/Yc** ve ilişkili .obj dosyası stdafx.obj önce işlenir, bağlayıcı LNK4221 atar.  
  
 Tek yönlü Bu sorun olduğu için her önceden derlenmiş üstbilgi emin olmak için çözümlemek için kendisiyle içeren yalnızca bir kaynak dosya yok **/Yc**. Diğer tüm kaynak dosyaları önceden derlenmiş başlıklar kullanmalıdır. Bu ayar değiştirme hakkında daha fazla bilgi için bkz: [/Yu (önceden derlenmiş üst bilgi dosyasını kullanma)](../../build/reference/yu-use-precompiled-header-file.md).