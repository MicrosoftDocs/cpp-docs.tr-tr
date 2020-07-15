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
ms.openlocfilehash: 135d919278c8e969dc3a31381d5abbd1058c8663
ms.sourcegitcommit: 31a443c9998cf5cfbaff00fcf815b133f55b2426
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86373898"
---
# <a name="tsaware-create-terminal-server-aware-application"></a>/TSAWARE (Terminal Sunucusu Algılayan Uygulama Oluştur)

```
/TSAWARE[:NO]
```

## <a name="remarks"></a>Açıklamalar

/TSAWARE seçeneği, program görüntüsünün isteğe bağlı üstbilgisindeki IMAGE_OPTIONAL_HEADER Dllözellikler alanında bir bayrak ayarlar. Bu bayrak ayarlandığında, Terminal sunucusu uygulamada belirli değişiklikler yapmayacak.

Bir uygulama, Terminal Server 'ın farkında olmadığında (eski uygulama olarak da bilinir), Terminal sunucusu, eski uygulamada, çok kullanıcılı bir ortamda düzgün çalışmasını sağlamak için bazı değişiklikler yapar. Örneğin, Terminal sunucusu, her kullanıcının sistem Windows dizinini almak yerine bir Windows klasörü aldığından, bir sanal Windows klasörü oluşturacaktır. Bu, kullanıcılara kendi ıNı dosyalarına erişim sağlar. Ayrıca, Terminal sunucusu eski bir uygulama için kayıt defterinde bazı ayarlamalar yapar. Bu değişiklikler, Terminal Server 'da eski uygulamanın yüklenmesini yavaşlatır.

Bir uygulama Terminal Server 'ı kullanıyorsa, bu, ıNı dosyalarını kullanmaz veya kurulum sırasında **HKEY_CURRENT_USER** kayıt defterine yazmalıdır.

/TSAWARE kullanıyorsanız ve uygulamanız hala ıNı dosyalarını kullanıyorsa, dosyalar sistemin tüm kullanıcıları tarafından paylaşılır. Bu kabul edilebilir ise, uygulamanızı/T saware ile bağlayabilirsiniz. Aksi takdirde,/T saware: NO kullanmanız gerekir.

/T saware seçeneği, Windows ve konsol uygulamaları için varsayılan olarak etkindir. Bilgi için bkz. [/Subsystem](subsystem-specify-subsystem.md) ve [/Version](version-version-information.md) .

/TSAWARE, sürücüler veya dll 'Ler için geçerli değildir.

Bir uygulama/T saware ile bağlanmışsa, DUMPBIN [/Headers](headers.md) bu etkiye ilişkin bilgileri görüntüler.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörüne tıklayın.

1. **Sistem** Özellik sayfasına tıklayın.

1. **Terminal sunucusu** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.TerminalServerAware%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)<br/>
[Kullanıcıya özgü bilgileri depolama](/windows/win32/TermServ/storing-user-specific-information)<br/>
[Terminal Hizmetleri ortamındaki eski uygulamalar](https://docs.microsoft.com/previous-versions//aa382957(v=vs.85))
