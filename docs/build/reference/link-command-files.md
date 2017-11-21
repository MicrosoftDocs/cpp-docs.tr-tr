---
title: "LINK komut dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: link
dev_langs: C++
helpviewer_keywords:
- syntax, LINK command files
- command files [C++]
- LINK tool [C++]
- text files, passing arguments to LINK
- LINK tool [C++], command-line syntax
- command files [C++], LINK
ms.assetid: 7154511c-32b9-4e5b-a515-3922fa9de48e
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2b6543cbb54dc982b1e55be8c0c554a429410b78
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="link-command-files"></a>LINK Komut Dosyaları
Komut satırı bağımsız değişkenleri, bir komut dosyası biçiminde bağlantısına geçirebilirsiniz. Bağlayıcı için bir komut dosyası belirtmek için aşağıdaki sözdizimini kullanın:  
  
```  
LINK @commandfile  
```  
  
 `commandfile` Bir metin dosyasının adıdır. Arasında hiç boşluk veya sekmesinde izin at işareti (@) ve dosya adı. Hiçbir varsayılan uzantı yoktur; Tüm uzantısı dahil tam dosya adı belirtmelisiniz. Joker karakterler kullanılamaz. Dosya adı ile mutlak veya göreli bir yol belirtebilirsiniz. BAĞLANTI dosyayı aramak için bir ortam değişkeni kullanmaz.  
  
 Komut dosyasında bağımsız değişkenleri alanları veya sekmelerle (komut satırında gibi) ayrılabilir ve yeni satır karakterlerini tarafından.  
  
 Bir komut dosyası, komut satırında bir bölümünü veya tümünü belirtebilirsiniz. Bir bağlantı komutta birden fazla komut dosyası kullanabilirsiniz. Komut satırında o konumda belirtilmiş olması durumunda gibi bağlantı komut dosyası girişi kabul eder. Komut dosyaları iç içe olamaz. BAĞLANTI görüntülemektedir komut dosyaları, içeriğini sürece [/nologo](../../build/reference/nologo-suppress-startup-banner-linker.md) seçeneği belirtildi.  
  
## <a name="example"></a>Örnek  
 DLL oluşturmak için aşağıdaki komutu ayrı komut dosyaları nesne dosyaları ve kitaplıkları adları geçirir ve kullandığı dosya/dışarı aktarmalar seçeneği belirtimi için üçüncü komut:  
  
```  
link /dll @objlist.txt @liblist.txt @exports.txt  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)