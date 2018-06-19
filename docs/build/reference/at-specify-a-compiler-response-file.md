---
title: '@ (Derleyici yanıt dosyasını belirtin) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- '@'
dev_langs:
- C++
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f291ed9a0ccc86ea1ef6fe6703205d76cdcd0fa1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32369584"
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
  
 Belirlemek mümkün değil **@** içinde bir yanıt dosyası seçenek gelen. Diğer bir deyişle, bir yanıt dosyası başka bir yanıt dosyası eklenemiyor.  
  
 Komut satırından kadar yanıt dosyası seçenekleri belirtebilirsiniz (örneğin, `@respfile.1 @respfile.2`) istediğiniz kadar.  
  
### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için  
  
-   Bir yanıt dosyası gelen geliştirme ortamında belirtilemez ve komut satırında belirtilmesi gerekir.  
  
### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için  
  
-   Bu derleyici seçeneği programlı olarak değiştirilemez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Seçenekleri](../../build/reference/compiler-options.md)   
 [Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)