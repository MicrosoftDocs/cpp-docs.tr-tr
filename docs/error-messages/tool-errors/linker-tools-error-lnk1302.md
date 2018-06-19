---
title: Bağlayıcı araçları hatası LNK1302 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa84a411f91303c84acb44e2e6c0ab3d975e19f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299425"
---
# <a name="linker-tools-error-lnk1302"></a>Bağlayıcı Araçları Hatası LNK1302
yalnızca güvenli .netmodules bağlama destekler; dosya .netmodule bağlantı kurulamıyor  
  
 Bir .netmodule (ile derlenmiş **/LN**) bağlayıcıya MSIL bağlantılandırma çağırmak için bir kullanıcı girişimi geçirildi.  C++ modülü ile derlenmiş ise MSIL bağlantılandırma için geçerli **/CLR: safe**.  
  
 İle bu hatayı düzeltmek için derleme **/CLR: safe** MSIL bağlantılandırma etkinleştirmek veya geçirmek için **/CLR** veya **/CLR: pure** modül yerine bağlayıcı .obj dosyasına.  
  
 Daha fazla bilgi için bkz.  
  
-   [/LN (MSIL Modülü Oluştur)](../../build/reference/ln-create-msil-module.md)  
  
-   [Bağlayıcı Girişi olarak .netmodule Dosyaları](../../build/reference/netmodule-files-as-linker-input.md)