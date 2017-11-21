---
title: "Bağlayıcı araçları hatası LNK1302 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1302
dev_langs: C++
helpviewer_keywords: LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7154cc538e17050eafec251729cf26a3cd62e573
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302
yalnızca güvenli .netmodules bağlama destekler; dosya .netmodule bağlantı kurulamıyor  
  
 Bir .netmodule (ile derlenmiş **/LN**) bağlayıcıya MSIL bağlantılandırma çağırmak için bir kullanıcı girişimi geçirildi.  C++ modülü ile derlenmiş ise MSIL bağlantılandırma için geçerli **/CLR: safe**.  
  
 İle bu hatayı düzeltmek için derleme **/CLR: safe** MSIL bağlantılandırma etkinleştirmek veya geçirmek için **/CLR** veya **/CLR: pure** modül yerine bağlayıcı .obj dosyasına.  
  
 Daha fazla bilgi için bkz.  
  
-   [/LN (MSIL modülü Oluştur)](../../build/reference/ln-create-msil-module.md)  
  
-   [Bağlayıcı girişi olarak .netmodule dosyaları](../../build/reference/netmodule-files-as-linker-input.md)