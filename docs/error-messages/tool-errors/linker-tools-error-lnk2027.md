---
title: Bağlayıcı araçları hatası LNK2027 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156310a0d21651b9fd2ee6002ace419db4996681
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027
Çözümlenmemiş modülü Başvurusu 'module'  
  
 Bağlayıcı için geçirilen dosya ile belirtilen bir modülde bir bağımlılığa sahip **/ASSEMBLYMODULE** veya doğrudan bağlayıcıya geçirildi.  
  
 LNK2027 gidermek için aşağıdakilerden birini yapın:  
  
-   Bağlayıcı modülü bağımlılık sahip bir dosya geçmeyin.  
  
-   Modülüyle belirtin **/ASSEMBLYMODULE**.  
  
-   Modül güvenli .netmodule ise, modül doğrudan bağlayıcıya geçirme.  
  
 Daha fazla bilgi için bkz: [/ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).