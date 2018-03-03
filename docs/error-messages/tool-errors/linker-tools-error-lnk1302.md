---
title: "Bağlayıcı araçları hatası LNK1302 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2a5b9201608d6d457288c7ade9376147da08bcb9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302
yalnızca güvenli .netmodules bağlama destekler; dosya .netmodule bağlantı kurulamıyor  
  
 Bir .netmodule (ile derlenmiş **/LN**) bağlayıcıya MSIL bağlantılandırma çağırmak için bir kullanıcı girişimi geçirildi.  C++ modülü ile derlenmiş ise MSIL bağlantılandırma için geçerli **/CLR: safe**.  
  
 İle bu hatayı düzeltmek için derleme **/CLR: safe** MSIL bağlantılandırma etkinleştirmek veya geçirmek için **/CLR** veya **/CLR: pure** modül yerine bağlayıcı .obj dosyasına.  
  
 Daha fazla bilgi için bkz.  
  
-   [/LN (MSIL modülü Oluştur)](../../build/reference/ln-create-msil-module.md)  
  
-   [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)