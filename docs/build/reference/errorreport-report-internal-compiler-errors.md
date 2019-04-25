---
title: /errorReport (Dahili Derleme Hatalarını Raporla)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.ErrorReporting
- /errorreport
helpviewer_keywords:
- /errorReport compiler option [C++]
- -errorReport compiler option [C++]
ms.assetid: 819828f8-b0a5-412c-9c57-bf822f17e667
ms.openlocfilehash: 52909cb42180bf8b778d73fd709be05faf3f5714
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62271794"
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

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **C/C++** klasör.

1. Tıklayın **Gelişmiş** özellik sayfası.

1. Değiştirme **hata raporlama** özelliği.

### <a name="to-set-this-compiler-option-programmatically"></a>Bu derleyici seçeneğini program üzerinden ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.ErrorReporting%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC Derleyicisi Seçenekleri](compiler-options.md)<br/>
[MSVC Derleyicisi Komut Satırı Söz Dizimi](compiler-command-line-syntax.md)
