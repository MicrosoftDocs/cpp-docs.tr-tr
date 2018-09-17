---
title: -errorReport (dahili derleme hatalarını raporla) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
dev_langs:
- C++
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0c96225e566593987bef8ec9a82c73daacfcefb6
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45720115"
---
# <a name="errorreport-report-internal-compiler-errors"></a>/errorReport (Dahili Derleme Hatalarını Raporla)

Derleyici iç hatası (ICE) bilgilerini doğrudan Microsoft'a sağlamanıza olanak tanır.

## <a name="syntax"></a>Sözdizimi

```
/errorReport:[ none | prompt | queue | send ]
```

## <a name="arguments"></a>Arguments

**Yok**<br/>
Derleyici iç hatalarıyla ilgili raporlar toplanmaz ve Microsoft'a gönderilir.

**istemi**<br/>
Derleyici iç hatası aldığınızda rapor göndermek isteyip istemediğinizi sorar. **İstemi** geliştirme ortamında uygulama derlendiğinde varsayılandır.

**Kuyruk**<br/>
Hata raporunu kuyruğa alır. Böylece son kez oturum açtıktan sonra herhangi bir hata rapor, yönetici ayrıcalıklarıyla oturum açtığınızda, bir pencere görüntülenir (, üç günde birden çok kez hata raporu göndermek isteyip istemediğiniz değil). **Kuyruk** bir komut isteminde uygulama derlendiğinde varsayılandır.

**Gönder**<br/>
Otomatik olarak raporlama tarafından Windows hata bildirimi sistem ayarları etkinse, derleyici iç hata raporlarını Microsoft'a gönderir.

## <a name="remarks"></a>Açıklamalar

Derleyici bir kaynak kodu dosyasını işlerken bir iç derleyici hatası (ICE) sonuçlanır. Bir ICE ortaya çıktığında, derleyici bir çıktı dosyasını veya kodunuzu düzeltmek için kullanabileceğiniz herhangi bir kullanışlı tanılama üretmez.

Bir ICE var olduğunda daha önceki sürümlerde, sorunu bildirmek için Microsoft Ürün Destek Hizmetleri çağırmak için önerilir. İle **/errorreport**, doğrudan Microsoft'a ICE bilgi sağlayabilir. Hata raporları, gelecekteki derleyici sürümleri artırmaya yardımcı olabilir.

Bir kullanıcının yeteneğini raporları göndermek için bilgisayar ve kullanıcı ilkesi izinlerine bağlıdır.

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **hata raporlama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)