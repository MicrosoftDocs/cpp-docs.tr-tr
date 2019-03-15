---
title: /TSAWARE (Terminal Sunucusu Algılayan Uygulama Oluştur)
ms.date: 11/04/2016
f1_keywords:
- /tsaware
- VC.Project.VCLinkerTool.TerminalServerAware
helpviewer_keywords:
- Terminal Server
- /TSAWARE linker option
- Terminal Server, Terminal Server-aware applications
- -TSAWARE linker option
- TSAWARE linker option
ms.assetid: fe1c1846-de5b-4839-b562-93fbfe36cd29
ms.openlocfilehash: f6ed6184f8ae4b3a0f9db3c1f962a2918a185138
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57816951"
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

/ TSAWARE seçeneği, Windows ve konsol uygulamaları için varsayılan olarak etkindir. Bkz: [/Subsystem](subsystem-specify-subsystem.md) ve [/VERSION](version-version-information.md) bilgi.

/ TSAWARE, sürücüleri, VxD veya dll için geçerli değil.

/ TSAWARE ile DUMPBIN uygulamanın bağlı olduğu [OPTIONAL](headers.md) belirlememişse bu bağlamda bilgileri görüntüler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Tıklayın **bağlayıcı** klasör.

1. Tıklayın **sistem** özellik sayfası.

1. Değiştirme **Terminal sunucusu** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[Kullanıcıya özgü bilgileri depolayan](/windows/desktop/TermServ/storing-user-specific-information)<br/>
[Terminal Hizmetleri ortamında eski uygulamaları](https://msdn.microsoft.com/library/aa382957.aspx)
