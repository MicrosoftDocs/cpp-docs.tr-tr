---
title: Bağlayıcı araçları hatası LNK1123 | Microsoft Docs
ms.custom: ''
ms.date: 12/29/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1123
dev_langs:
- C++
helpviewer_keywords:
- LNK1123
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b12a65e61c5677943b4ea1b4b85c12cfc796af45
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33300283"
---
# <a name="linker-tools-error-lnk1123"></a>Bağlayıcı Araçları Hatası LNK1123

> COFF dönüştürme sırasında hata: geçersiz veya bozuk dosya

Giriş dosyaları Ortak Nesne Dosyası Biçimi (COFF) biçiminde olmalıdır. Bir giriş dosyası COFF değilse, bağlayıcı otomatik olarak 32-bit OMF nesnelerini COFF 'a dönüştürmeyi dener veya kaynak dosyalarını dönüştürmek için CVTRES.EXE 'yi çalıştırır. Bu ileti, bağlayıcının dosyayı dönüştüremediğini gösterir. Bu ayrıca CVTRES uyumsuz sürümü kullanılırken oluşabilir. EXE Visual Studio, Windows Geliştirme Seti ya da .NET Framework başka bir yükleme.

> [!NOTE]
> Visual Studio'nun önceki sürümünü çalıştırıyorsanız, otomatik dönüştürme desteklenmiyor olabilir.

## <a name="to-fix-the-problem"></a>Sorunu gidermek için

- Tüm hizmet paketlerini ve güncelleştirmelerini Visual Studio sürümü için geçerlidir. Bu Visual Studio 2010 için özellikle önemlidir.

- Yapı devre dışı artımlı bağlama ile deneyin. Menü çubuğunda seçin **proje**, **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri**, **bağlayıcı**. Değerini değiştirme **etkinleştirmek artımlı bağlantılandırma** için **Hayır**.

- Doğrulayın CVTRES sürümü. EXE bulunan ilk projeniz tarafından kullanılan Platform araç takımı sürümünü veya derleme araçları sürümü, PATH ortam değişkeni eşleşir.

- Bildirimi katıştırmak seçeneğini kapatma deneyin. Menü çubuğunda seçin **proje**, **özellikleri**. İçinde **özellik sayfaları** iletişim kutusunda, genişletin **yapılandırma özellikleri**, **bildirim aracı**, **giriş ve çıkış**. Değerini değiştirme **katıştırmak bildirim** için **Hayır**.

- Dosya türünün geçerli olduğundan emin olun. Örneğin, bir OMF nesnesinin 16-bit olmadığından ve 32-bit olduğundan emin olun. Daha fazla bilgi için bkz: [. Bağlayıcı girişi olarak obj dosyaları](../../build/reference/dot-obj-files-as-linker-input.md) ve [PE biçimi](https://msdn.microsoft.com/library/windows/desktop/ms680547).

- Dosyanın bozuk olmadığından emin olun. Gerekirse, yeniden oluşturun.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Girişi olarak .Def Dosyaları](../../build/reference/dot-obj-files-as-linker-input.md)  
[EDITBIN Başvurusu](../../build/reference/editbin-reference.md)  
[DUMPBIN Başvurusu](../../build/reference/dumpbin-reference.md)  
