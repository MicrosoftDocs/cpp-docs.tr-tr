---
title: "Bağlayıcı araçları hatası LNK2027 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2027
dev_langs: C++
helpviewer_keywords: LNK2027
ms.assetid: e2f857a8-8e8a-4697-bbff-12ccb84a35c1
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b9cefb948ffd09421a6d4a9c1c540ef22f8736fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk2027"></a>Bağlayıcı Araçları Hatası LNK2027
Çözümlenmemiş modülü Başvurusu 'module'  
  
 Bağlayıcı için geçirilen dosya ile belirtilen bir modülde bir bağımlılığa sahip **/ASSEMBLYMODULE** veya doğrudan bağlayıcıya geçirildi.  
  
 LNK2027 gidermek için aşağıdakilerden birini yapın:  
  
-   Bağlayıcı modülü bağımlılık sahip bir dosya geçmeyin.  
  
-   Modülüyle belirtin **/ASSEMBLYMODULE**.  
  
-   Modül güvenli .netmodule ise, modül doğrudan bağlayıcıya geçirme.  
  
 Daha fazla bilgi için bkz: [/ASSEMBLYMODULE (derlemeye MSIL Modülü Ekle)](../../build/reference/assemblymodule-add-a-msil-module-to-the-assembly.md) ve [bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md).