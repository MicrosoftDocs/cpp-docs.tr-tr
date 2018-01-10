---
title: "Bağlayıcı araçları hatası LNK1181 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1181
dev_langs: C++
helpviewer_keywords: LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8f5092d4f3ce7b4f96ca4dc5c1554483a7fc3a0b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1181"></a>Bağlayıcı Araçları Hatası LNK1181
Giriş dosyası 'filename' açılamıyor  
  
 Bağlayıcı bulunamadı `filename` var olmadığı veya yolu bulunamadı.  
  
 Bazı yaygın nedenler hatası LNK1181 eklemek için:  
  
-   `filename`Bağlayıcı satır, ancak dosyayı ek bir bağımlılığı yok olarak başvurulur.  
  
-   A **/Libpath** dizinini içeren belirtir deyimi `filename` eksik.  
  
 Yukarıdaki sorunları gidermek için bağlayıcı satırında başvurulan tüm dosyaları sistemde emin olun.  Ayrıca olduğundan emin bir **/Libpath** deyimi içeren bir bağlayıcı bağımlı dosya her dizin için.  
  
 Başka bir olası LNK1181 uzun bir dosya adı boşluklar ile tırnak işaretleri içine nedeni.  Bu durumda, bağlayıcı yalnızca bir dosya adına kadar ilk alanı tanıması ve bir dosya uzantısı varsayalım. obj.  Bu durum için uzun dosya adını tırnak içine çözümdür (yolu ve dosya adı) tırnak işaretleri içindeki.  
  
 Daha fazla bilgi için bkz: [bağlayıcı girişi olarak .lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/ LIBPATH (ek Libpath)](../../build/reference/libpath-additional-libpath.md)