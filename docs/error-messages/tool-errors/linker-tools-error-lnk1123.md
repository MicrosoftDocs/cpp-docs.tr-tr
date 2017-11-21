---
title: "Bağlayıcı araçları hatası LNK1123 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1123
dev_langs: C++
helpviewer_keywords: LNK1123
ms.assetid: fe47af69-0f42-4792-9133-541192cd8514
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ade68d51125167c34fc46f23a7c9ce7eccfdef5f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1123"></a>Bağlayıcı Araçları Hatası LNK1123
COFF dönüştürme sırasında hata: geçersiz veya bozuk dosya  
  
 Giriş dosyaları Ortak Nesne Dosyası Biçimi (COFF) biçiminde olmalıdır. Bir giriş dosyası COFF değilse, bağlayıcı otomatik olarak 32-bit OMF nesnelerini COFF 'a dönüştürmeyi dener veya kaynak dosyalarını dönüştürmek için CVTRES.EXE 'yi çalıştırır. Bu ileti, bağlayıcının dosyayı dönüştüremediğini gösterir. Bu ayrıca CVTRES uyumsuz sürümü kullanılırken oluşabilir. EXE Visual Studio, Windows Geliştirme Seti ya da .NET Framework başka bir yükleme.  
  
> [!NOTE]
>  Visual Studio'nun önceki sürümünü çalıştırıyorsanız, otomatik dönüştürme desteklenmiyor olabilir.  
  
### <a name="to-fix-the-problem"></a>Sorunu gidermek için  
  
-   Tüm hizmet paketlerini ve güncelleştirmelerini Visual Studio sürümü için geçerlidir. Bu Visual Studio 2010 için özellikle önemlidir.  
  
-   Yapı devre dışı artımlı bağlama ile deneyin. Menü çubuğunda seçin **proje**, **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri**, **bağlayıcı**. Değerini değiştirme **etkinleştirmek artımlı bağlantılandırma** için **Hayır**.  
  
-   Doğrulayın CVTRES sürümü. EXE bulunan ilk projeniz tarafından kullanılan Platform araç takımı sürümünü veya derleme araçları sürümü, PATH ortam değişkeni eşleşir.  
  
-   Bildirimi katıştırmak seçeneğini kapatma deneyin. Menü çubuğunda seçin **proje**, **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri**, **bildirim aracı**, **giriş ve çıkış**. Değerini değiştirme **katıştırmak bildirim** için **Hayır**.  
  
-   Dosya türünün geçerli olduğundan emin olun. Örneğin, bir OMF nesnesinin 16-bit olmadığından ve 32-bit olduğundan emin olun. Daha fazla bilgi için bkz: [. Bağlayıcı girişi olarak obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md) ve [Microsoft PE ve COFF belirtimi](http://go.microsoft.com/fwlink/p/?LinkId=93292).  
  
-   Dosyanın bozuk olmadığından emin olun. Gerekirse, yeniden oluşturun.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [. Bağlayıcı girişi olarak obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)   
 [EDITBIN başvurusu](../../build/reference/editbin-reference.md)   
 [DUMPBIN başvurusu](../../build/reference/dumpbin-reference.md)