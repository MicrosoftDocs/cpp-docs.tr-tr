---
title: "@ (Derleyici yanıt dosyasını belirtin) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: '@'
dev_langs: C++
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: fcbadb55b2116b0939bbb954e4f544c40caacebb
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="-specify-a-compiler-response-file"></a>@ (Derleyici Yanıt Dosyasını Belirt)
Derleyici yanıt dosyasını belirtir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
@response_file  
```  
  
## <a name="arguments"></a>Arguments  
 `response_file`  
 Derleyici komutları içeren bir metin dosyası.  
  
## <a name="remarks"></a>Açıklamalar  
 Bir yanıt dosyası, komut satırında belirtirsiniz herhangi bir komut içerebilir. Bu, komut satırı bağımsız değişkenlerini en fazla 127 karakter durumlarda yararlı olabilir.  
  
 Belirlemek mümkün değil  **@**  içinde bir yanıt dosyası seçenek gelen. Diğer bir deyişle, bir yanıt dosyası başka bir yanıt dosyası eklenemiyor.  
  
 Komut satırından kadar yanıt dosyası seçenekleri belirtebilirsiniz (örneğin, `@respfile.1 @respfile.2`) istediğiniz kadar.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
-   Bir yanıt dosyası gelen geliştirme ortamında belirtilemez ve komut satırında belirtilmesi gerekir.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bu derleyici seçeneği programlı olarak değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici seçeneklerini ayarlama](../../build/reference/setting-compiler-options.md)