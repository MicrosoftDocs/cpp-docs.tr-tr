---
title: "Bağlayıcı araçları hatası LNK2027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK2027
dev_langs:
- C++
helpviewer_keywords:
- LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 554dac121c066dac4c05685be1b937298344a76a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027
Çözümlenmemiş modülü Başvurusu 'module'  
  
 Bağlayıcı için geçirilen dosya ile belirtilen bir modülde bir bağımlılığa sahip **/ASSEMBLYMODULE** veya doğrudan bağlayıcıya geçirildi.  
  
 LNK2027 gidermek için aşağıdakilerden birini yapın:  
  
-   Bağlayıcı modülü bağımlılık sahip bir dosya geçmeyin.  
  
-   Modülüyle belirtin **/ASSEMBLYMODULE**.  
  
-   Modül güvenli .netmodule ise, modül doğrudan bağlayıcıya geçirme.  
  
 Daha fazla bilgi için bkz: [/ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).