---
title: -TSAWARE (Terminal sunucusu algılayan uygulama oluştur) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
dev_langs:
- C++
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac9aeaaf4ccaaf3f813adbf9f65eb3db7df353f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45723956"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (Terminal Sunucusu Algılayan Uygulama Oluştur)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>Açıklamalar

/ TSAWARE seçeneği program görüntüsünün isteğe bağlı üst bilgisindeki ımage_optıonal_header DllCharacteristics alanında bir bayrak ayarlar. Bu bayrak ayarlandığında Terminal sunucusu uygulamada bazı değişiklikler yapmaz.

Terminal sunucusu kullanan (eski bir uygulama olarak da bilinir) bir uygulama olmadığı durumlarda, Terminal sunucusu çok kullanıcılı bir ortamda düzgün çalışması için eski uygulamayı bazı değişiklikler yapar. Örneğin, her kullanıcı bir Windows klasörü sisteminin Windows dizini alınırken yerine alır, Terminal sunucusu sanal bir Windows klasörü oluşturun. Bu kullanıcıların kendi INİ dosyaları için erişim sağlar. Ayrıca, Terminal sunucusu kayıt defteri eski bir uygulama için bazı ayarlamalar yapar. Bu değişiklikler, Terminal sunucusu üzerinde eski uygulamayı yüklenmesini yavaş.

Terminal sunucusu kullanan bir uygulama ise, gerekir INI dosyalarına dayanan ne yazma **HKEY_CURRENT_USER** Kurulum sırasında kayıt defteri.

/ TSAWARE kullandığınız ve uygulamanızı INİ dosyaları yine de kullanıyorsa, dosya sisteminin tüm kullanıcılar tarafından paylaşılır. Kabul edilebilir ise, / TSAWARE uygulamanızla hala bağlantı oluşturabilirsiniz; Aksi takdirde: No kullanmanız gerekir.

/ TSAWARE seçeneği, Windows ve konsol uygulamaları için varsayılan olarak etkindir. Bkz: [/Subsystem](../../build/reference/subsystem-specify-subsystem.md) ve [/VERSION](../../build/reference/version-version-information.md) bilgi.

/ TSAWARE, sürücüleri, VxD veya dll için geçerli değil.

/ TSAWARE ile DUMPBIN uygulamanın bağlı olduğu [OPTIONAL](../../build/reference/headers.md) belirlememişse bu bağlamda bilgileri görüntüler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **Terminal sunucusu** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)<br/>
[Kullanıcıya özgü bilgileri depolayan](/windows/desktop/TermServ/storing-user-specific-information)<br/>
[Terminal Hizmetleri ortamında eski uygulamaları](https://msdn.microsoft.com/library/aa382957.aspx)