---
title: XDCMake başvurusu | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- xdcmake
dev_langs:
- C++
helpviewer_keywords:
- xdcmake program
ms.assetid: 14e65747-d000-4343-854b-8393bf01cbac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 383347dc5cd1ce0dcadff6bdee802b90fd52e85d
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/01/2018
ms.locfileid: "33333911"
---
# <a name="xdcmake-reference"></a>XDCMake Başvurusu
xdcmake.exe .xdc dosyalarını bir .xml dosyasına derler bir programdır. Kaynak kodu ile derlenen bir .xdc dosyası her kaynak kodu dosyasının Visual C++ derleyicisi tarafından oluşturulduğunda [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) ve kaynak kodu dosyasının XML etiketleriyle artırıldığında belge açıklamaları içerdiğinde.  
  
### <a name="to-use-xdcmakeexe-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında xdcmake.exe kullanmak için  
  
1.  Projenin açmak **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [proje özellikleriyle çalışma](../ide/working-with-project-properties.md).  
  
2.  Açık **yapılandırma özellikleri** klasör.  
  
3.  Tıklatın **XML belge açıklamaları** özellik sayfası.  
  
> [!NOTE]
>  xdcmake.exe geliştirme ortamı (özellik sayfaları) kullanıldığında xdcmake.exe seçenekleri komut satırı seçeneklerinden farklılık gösterir. Geliştirme ortamında xdcmake.exe kullanma hakkında daha fazla bilgi için bkz: [XML belgesi oluşturma aracı özellik sayfaları](../ide/xml-document-generator-tool-property-pages.md).  
  
## <a name="syntax"></a>Sözdizimi  
 xdcmake `input_filename options`  
  
## <a name="parameters"></a>Parametreler  
 burada:  
  
 `input_filename`  
 Xdcmake.exe giriş olarak kullanılan .xdc dosyaları dosya adı. Bir veya daha fazla .xdc dosyaları belirtin veya *.xdc geçerli dizindeki tüm .xdc dosyaları kullanın.  
  
 `options`  
 Sıfır veya daha fazlasını:  
  
|Seçenek|Açıklama|  
|------------|-----------------|  
|/?, / Yardım|Xdcmake.exe için yardımı görüntüler.|  
|/Assembly:*dosya adı*|Değerini belirtmenize olanak sağlar. \<derleme > .xml dosyasındaki etiketi.  Varsayılan olarak, değerini \<derleme > etiketi .xml dosyasının dosya adı ile aynı değil.|  
|/nologo|Telif hakkı iletisi engelleyin.|  
|/ out:*dosya adı*|.Xml dosyasının adını belirtmenize olanak sağlar.  Varsayılan olarak, .xml dosyasını xdcmake.exe tarafından işlenen ilk .xdc dosyanın adıdır.|  
  
## <a name="remarks"></a>Açıklamalar  
 Visual Studio proje oluştururken xdcmake.exe otomatik olarak çağırır. Komut satırında xdcmake.exe de çalıştırabilirsiniz.  
  
 Bkz: [belge açıklamaları için önerilen etiketler](../ide/recommended-tags-for-documentation-comments-visual-cpp.md) belge açıklamaları için kaynak kodu dosyaları ekleme hakkında daha fazla bilgi için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)