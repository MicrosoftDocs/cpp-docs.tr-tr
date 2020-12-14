---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları hata LNK1123'
title: Bağlayıcı Araçları Hatası LNK1123
ms.date: 12/29/2017
f1_keywords:
- LNK1123
helpviewer_keywords:
- LNK1123
ms.openlocfilehash: f9ee04a8e46c34e6ac5133c90488ed49619734d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281372"
---
# <a name="linker-tools-error-lnk1123"></a>Bağlayıcı Araçları Hatası LNK1123

> COFF dönüştürme sırasında hata: geçersiz veya bozuk dosya

Giriş dosyaları Ortak Nesne Dosyası Biçimi (COFF) biçiminde olmalıdır. Bir giriş dosyası COFF değilse, bağlayıcı otomatik olarak 32-bit OMF nesnelerini COFF 'a dönüştürmeyi dener veya kaynak dosyalarını dönüştürmek için CVTRES.EXE 'yi çalıştırır. Bu ileti, bağlayıcının dosyayı dönüştüremediğini gösterir. Bu, Visual Studio 'nun başka bir yüklemesinden, Windows geliştirme seti 'nden veya .NET Framework uyumsuz bir CVTRES.EXE sürümü kullanılırken de oluşabilir.

> [!NOTE]
> Visual Studio'nun önceki sürümünü çalıştırıyorsanız, otomatik dönüştürme desteklenmiyor olabilir.

## <a name="to-fix-the-problem"></a>Sorunu gidermek için

- Visual Studio sürümünüz için tüm hizmet paketlerini ve güncelleştirmeleri uygulayın. Visual Studio 2010 için bu özellikle önemlidir.

- Artımlı bağlama devre dışı ile oluşturmayı deneyin. Menü çubuğunda, **Proje**, **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**, **bağlayıcı**' yı genişletin. **Artımlı bağlamayı** **Hayır** olarak değiştirme değerini değiştirin.

- PATH ortam değişkeninizdeki ilk olarak bulunan CVTRES.EXE sürümünün derleme araçlarının sürümü veya projeniz tarafından kullanılan platform araç takımı sürümü ile eşleştiğini doğrulayın.

- Ekleme bildirimi seçeneğini kapatmayı deneyin. Menü çubuğunda, **Proje**, **Özellikler**' i seçin. **Özellik sayfaları** iletişim kutusunda, **yapılandırma özellikleri**, **bildirim aracı**, **giriş ve çıkış**' ı genişletin. **Ekleme bildiriminin** değerini **Hayır** olarak değiştirin.

- Dosya türünün geçerli olduğundan emin olun. Örneğin, bir OMF nesnesinin 16-bit olmadığından ve 32-bit olduğundan emin olun. Daha fazla bilgi için bkz [.. Bağlayıcı girişi](../../build/reference/dot-obj-files-as-linker-input.md) ve [PE biçimi](/windows/win32/Debug/pe-format)olarak obj dosyaları.

- Dosyanın bozuk olmadığından emin olun. Gerekirse yeniden derleyin.

## <a name="see-also"></a>Ayrıca bkz.

[. Bağlayıcı girişi olarak obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)<br/>
[EDITBIN Başvurusu](../../build/reference/editbin-reference.md)<br/>
[DUMPBIN başvurusu](../../build/reference/dumpbin-reference.md)
