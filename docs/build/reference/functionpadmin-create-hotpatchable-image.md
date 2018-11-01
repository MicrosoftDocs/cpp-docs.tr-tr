---
title: /FUNCTIONPADMIN (Düzeltme Eki Eklenebilen Görüntü Oluşturma)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: c1e84f308796eabcaea61518e3731f633c2f67e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474899"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Düzeltme Eki Eklenebilen Görüntü Oluşturma)

Görüntüyü düzeltme eki eklemek üzere hazırlar.

## <a name="syntax"></a>Sözdizimi

> **/ FUNCTIONPADMIN**[**:**_alanı_]

### <a name="arguments"></a>Arguments

*alanı*<br/>
Bayt cinsinden her işlevin başlangıcına eklemek için doldurma miktarı. X86 üzerinde bu 5 bayt doldurma Varsayılanları ve x64 üzerinde bu 6 bayt için varsayılan olarak. Diğer hedefler üzerinde bir değer belirtilmelidir.

## <a name="remarks"></a>Açıklamalar

Bir hotpatchable görüntü üretmek bağlayıcı için sırada .obj dosyaları ile derlenmiş olmalıdır [/hotpatch (düzeltme eki eklenebilen görüntü oluşturma)](../../build/reference/hotpatch-create-hotpatchable-image.md).

Derleme ve görüntü cl.exe, tek bir çağrı ile bağlantı **/hotpatch** gelir **/functionpadmin**.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Visual C++ proje özelliklerini ayarlama](../../ide/working-with-project-properties.md).

1. Seçin **yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** özellik sayfası.

1. Girin **/FUNCTIONPADMIN** seçeneğini **ek seçenekler**. Seçin **Tamam** yaptığınız değişiklikleri kaydedin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)
