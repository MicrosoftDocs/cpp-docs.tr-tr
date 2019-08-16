---
title: Bağlayıcı Araçları Hatası LNK1123
ms.date: 12/29/2017
f1_keywords:
- LNK1123
helpviewer_keywords:
- LNK1123
ms.openlocfilehash: 31fd634291bfb0af17348197ae8a6225ac490c89
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509907"
---
# <a name="linker-tools-error-lnk1123"></a>Bağlayıcı Araçları Hatası LNK1123

> COFF dönüştürme sırasında hata: geçersiz veya bozuk dosya

Giriş dosyaları Ortak Nesne Dosyası Biçimi (COFF) biçiminde olmalıdır. Bir giriş dosyası COFF değilse, bağlayıcı otomatik olarak 32-bit OMF nesnelerini COFF 'a dönüştürmeyi dener veya kaynak dosyalarını dönüştürmek için CVTRES.EXE 'yi çalıştırır. Bu ileti, bağlayıcının dosyayı dönüştüremediğini gösterir. Bu, uyumsuz bir CVTRES sürümü kullanılırken de oluşabilir. Visual Studio, Windows geliştirme seti veya .NET Framework başka bir yüklemesinden EXE.

> [!NOTE]
> Visual Studio'nun önceki sürümünü çalıştırıyorsanız, otomatik dönüştürme desteklenmiyor olabilir.

## <a name="to-fix-the-problem"></a>Sorunu gidermek için

- Visual Studio sürümünüz için tüm hizmet paketlerini ve güncelleştirmeleri uygulayın. Visual Studio 2010 için bu özellikle önemlidir.

- Artımlı bağlama devre dışı ile oluşturmayı deneyin. Menü çubuğunda, **Proje**, **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**, **bağlayıcı**' yı genişletin. **Artımlı bağlamayı** **Hayır**olarak değiştirme değerini değiştirin.

- CVTRES sürümünün olduğunu doğrulayın. İlk olarak, yol ortamınız değişkeninde bulunan EXE, derleme araçlarının sürümü ya da projeniz tarafından kullanılan platform araç takımının sürümü ile eşleşiyor.

- Ekleme bildirimi seçeneğini kapatmayı deneyin. Menü çubuğunda, **Proje**, **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**, **bildirim aracı**, **giriş ve çıkış**' ı genişletin. **Ekleme bildiriminin** değerini **Hayır**olarak değiştirin.

- Dosya türünün geçerli olduğundan emin olun. Örneğin, bir OMF nesnesinin 16-bit olmadığından ve 32-bit olduğundan emin olun. Daha fazla bilgi için bkz [. Bağlayıcı girişi](../../build/reference/dot-obj-files-as-linker-input.md) ve [PE biçimi](/windows/win32/Debug/pe-format)olarak obj dosyaları.

- Dosyanın bozuk olmadığından emin olun. Gerekirse yeniden derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Girişi olarak .Def Dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)<br/>
[EDITBIN Başvurusu](../../build/reference/editbin-reference.md)<br/>
[DUMPBIN Başvurusu](../../build/reference/dumpbin-reference.md)
