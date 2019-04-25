---
title: Bağlayıcı Araçları Hatası LNK1123
ms.date: 12/29/2017
f1_keywords:
- LNK1123
helpviewer_keywords:
- LNK1123
ms.openlocfilehash: b67a2a4ddad13988967b7cc7d827862a2a6fe933
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62255235"
---
# <a name="linker-tools-error-lnk1123"></a>Bağlayıcı Araçları Hatası LNK1123

> COFF dönüştürme sırasında hata: geçersiz veya bozuk dosya

Giriş dosyaları Ortak Nesne Dosyası Biçimi (COFF) biçiminde olmalıdır. Bir giriş dosyası COFF değilse, bağlayıcı otomatik olarak 32-bit OMF nesnelerini COFF 'a dönüştürmeyi dener veya kaynak dosyalarını dönüştürmek için CVTRES.EXE 'yi çalıştırır. Bu ileti, bağlayıcının dosyayı dönüştüremediğini gösterir. Bu ayrıca CVTRES uyumsuz bir sürümü kullanırken ortaya çıkabilir. Visual Studio, Windows Geliştirme Seti ya da .NET Framework başka bir yükleme EXE.

> [!NOTE]
> Visual Studio'nun önceki sürümünü çalıştırıyorsanız, otomatik dönüştürme desteklenmiyor olabilir.

## <a name="to-fix-the-problem"></a>Sorunu gidermek için

- Tüm hizmet paketleri ve güncelleştirmeler Visual Studio sürümünüz için geçerlidir. Bu Visual Studio 2010 için özellikle önemlidir.

- Yapı devre dışı artımlı bağlama ile deneyin. Menü çubuğunda, **proje**, **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**, **bağlayıcı**. Değiştirin **artımlı bağlamayı etkinleştir** için **Hayır**.

- Doğrulayın CVTRES sürümü. EXE bulunan derleme araçları sürümü veya projeniz tarafından kullanılan Platform araç kümesi sürümünü ilk uygulamanız yol ortam değişkeninde eşleşir.

- Bildirim ekleme seçeneğini kapatma deneyin. Menü çubuğunda, **proje**, **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda **yapılandırma özellikleri**, **bildirim aracında**, **giriş ve çıkış**. Değiştirin **ekleme bildirimi** için **Hayır**.

- Dosya türünün geçerli olduğundan emin olun. Örneğin, bir OMF nesnesinin 16-bit olmadığından ve 32-bit olduğundan emin olun. Daha fazla bilgi için [. Bağlayıcı girişi olarak obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md) ve [PE biçimi](/windows/desktop/Debug/pe-format).

- Dosyanın bozuk olmadığından emin olun. Gerekirse, yeniden oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Girişi olarak .Def Dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)<br/>
[EDITBIN Başvurusu](../../build/reference/editbin-reference.md)<br/>
[DUMPBIN Başvurusu](../../build/reference/dumpbin-reference.md)
