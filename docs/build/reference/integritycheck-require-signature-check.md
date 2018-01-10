---
title: -INTEGRITYCHECK (imza denetimi iste) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 9e738825-2c98-40cd-8ad2-5d0d9c14893e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7bf86676ecbc37e346f538d180612f21352fb48b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="integritycheck-require-signature-check"></a>/INTEGRITYCHECK (İmza Denetimi İste)
İkili görüntü dijital imzasını yükleme zamanında denetlenmesi gerektiğini belirtir.  
  
```  
/INTEGRITYCHECK[:NO]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, **/INTEGRITYCHECK** kapalıdır.  
  
 **/INTEGRITYCHECK** seçeneği ayarlar — DLL dosyası veya yürütülebilir dosyanın PE üstbilgisinde — Windows görüntüsünü yüklemek için bir dijital imza için denetlenecek bellek yöneticisi için bir bayrak. Bu seçeneğin, bazı Windows özellikleri tarafından yüklenen çekirdek modu kodunu uygulayan hem 32-bit hem de 64-bit DLL'ler için ayarlanması gerekir ve Windows Vista, [!INCLUDE[win7](../../build/includes/win7_md.md)], [!INCLUDE[win8](../../build/reference/includes/win8_md.md)], [!INCLUDE[winsvr08](../../build/reference/includes/winsvr08_md.md)] ve [!INCLUDE[winserver8](../../build/reference/includes/winserver8_md.md)] üzerindeki tüm aygıt sürücüleri için tavsiye edilir. Windows Vista'dan önceki Windows sürümlerinde bu bayrağı yok sayar. Daha fazla bilgi için bkz: [zorunlu bütünlüğü imzalama, taşınabilir yürütülebilir (PE) dosyaları](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx).  
  
### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneği ayarlamak için  
  
1.  Projeyi açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için bkz: [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  Genişletme **yapılandırma özellikleri** düğümü.  
  
3.  Genişletme **bağlayıcı** düğümü.  
  
4.  Seçin **komut satırı** özellik sayfası.  
  
5.  İçinde **ek seçenekler**, girin `/INTEGRITYCHECK` veya `/INTEGRITYCHECK:NO`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağlayıcı seçeneklerini ayarlama](../../build/reference/setting-linker-options.md)   
 [Bağlayıcı seçenekleri](../../build/reference/linker-options.md)   
 [Zorlanmış bütünlüğü imzalama, taşınabilir yürütülebilir (PE) dosyaları](http://social.technet.microsoft.com/wiki/contents/articles/255.forced-integrity-signing-of-portable-executable-pe-files.aspx)   
 [Çekirdek modu kod gözden geçirme imzalama](http://msdn.microsoft.com/windows/hardware/gg487328.aspx)   
 [Windows 7 ve Windows Server 2008 AppInit DLL'leri](http://msdn.microsoft.com/windows/hardware/gg463040.aspx)