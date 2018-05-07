---
title: Bağlayıcı araçları hatası LNK1181 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1181
dev_langs:
- C++
helpviewer_keywords:
- LNK1181
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 617678e5453acdafaf72875857b0e0f9b84a110a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk1181"></a>Bağlayıcı Araçları Hatası LNK1181
Giriş dosyası 'filename' açılamıyor  
  
 Bağlayıcı bulunamadı `filename` var olmadığı veya yolu bulunamadı.  
  
 Bazı yaygın nedenler hatası LNK1181 eklemek için:  
  
-   `filename` Bağlayıcı satır, ancak dosyayı ek bir bağımlılığı yok olarak başvurulur.  
  
-   A **/Libpath** dizinini içeren belirtir deyimi `filename` eksik.  
  
 Yukarıdaki sorunları gidermek için bağlayıcı satırında başvurulan tüm dosyaları sistemde emin olun.  Ayrıca olduğundan emin bir **/Libpath** deyimi içeren bir bağlayıcı bağımlı dosya her dizin için.  
  
 Başka bir olası LNK1181 uzun bir dosya adı boşluklar ile tırnak işaretleri içine nedeni.  Bu durumda, bağlayıcı yalnızca bir dosya adına kadar ilk alanı tanıması ve bir dosya uzantısı varsayalım. obj.  Bu durum için uzun dosya adını tırnak içine çözümdür (yolu ve dosya adı) tırnak işaretleri içindeki.  
  
 Daha fazla bilgi için bkz: [bağlayıcı girişi olarak .lib dosyaları](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [/LIBPATH (Ek Libpath)](../../build/reference/libpath-additional-libpath.md)