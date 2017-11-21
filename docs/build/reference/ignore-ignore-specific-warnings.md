---
title: "-Yoksay (belirli uyarıları atla) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /OVERWRITE
dev_langs: C++
helpviewer_keywords: /IGNORE linker option
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
caps.latest.revision: "3"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 496142cd483bab8ba58fe2ed6b31619616216bb4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ignore-ignore-specific-warnings"></a>/IGNORE (Belirli Uyarıları Atla)
```  
/IGNORE:warning[,warning]  
```  
  
## <a name="parameters"></a>Parametreler  
 `warning`  
 Bağlayıcı, 4000 için 4999 aralığında gizlemek için uyarı sayısı.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, tüm uyarıları bağlantı raporlar. Belirtin **yoksay:** `warning` belirli bir uyarı numarası gizlemek için bağlayıcı bildirmek için. Birden çok uyarıları yok saymak için uyarı numaralarını virgülle ayırın.  
  
 Bağlayıcı göz ardı yönelik bazı uyarılar izin vermiyor. Bu tabloda tarafından gizlenen olmayan uyarıların **Yoksay**:  
  
|Bağlayıcı uyarı||  
|--------------------|-|  
|LNK4017|`keyword`deyimi hedef platformu için desteklenmiyor; göz ardı|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|Tanınmayan seçenek '`option`'; yoksayıldı|  
|LNK4062|'`option`'ile uyumlu değil'`architecture`' hedef makine; göz ardı seçeneği|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|yoksayılıyor "`option1`"son için"`option2`" belirtimi|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|EntryPoint '`function`'ile __stdcall değil'`number`' bağımsız değişkenleri; bayt görüntü çalıştıramıyor|  
|LNK4088|/ Force seçeneği nedeniyle oluşturulan görüntü; Görüntü çalışmayabilir|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|seçeneğiyle belirtilen bağımsız değişken '`option`'; göz ardı anahtarı|  
|LNK4203|Program veritabanı okunurken hata oluştu '`filename`'; hiç hata ayıklama bilgileri gibi nesne bağlama|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' hata ayıklama modülü; başvurma bilgileri eksik olan hiçbir hata ayıklama bilgileri gibi nesne bağlama|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' modülü; başvuran için geçerli hata ayıklama bilgileri eksik hiçbir hata ayıklama bilgileri gibi nesne bağlama|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|önceden derlenmiş türü bilgileri; bulunamadı '`filename`' bağlantılı ya da üzerine; hiç hata ayıklama bilgileri gibi nesne bağlama|  
|LNK4207|'`filename`' /Yc /Yu /Z7 derlenmiş; hiç hata ayıklama bilgileri gibi PDB, / zi ile yeniden derleyebilirsiniz; bağlama nesnesi oluşturulamıyor|  
|LNK4208|uyumsuz PDB biçiminde '`filename`'; silin ve yeniden oluşturun; hiç hata ayıklama bilgileri gibi nesne bağlama|  
|LNK4209|hata ayıklama bilgileri bozuk; Modül derlenir; hata ayıklama bilgileri gibi nesne bağlama|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option`artık desteklenmemektedir; göz ardı|  
|LNK4228|'`option`' geçersiz bir DLL için; yoksayıldı|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|Geçersiz yönergesi /`directive` göz ardı; bulundu|  
  
 Genel olarak, yoksayılamaz bağlayıcı uyarılarını derleme hataları, komut satırı hataları veya sorununu çözer yapılandırma hataları temsil eder.  
  
### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../../ide/working-with-project-properties.md).  
  
2.  İçinde **bağlayıcı** klasöründe seçin **komut satırı** özellik sayfası.  
  
3.  Değiştirme **ek seçenekler** özelliği.  
  
### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için  
  
-   Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.