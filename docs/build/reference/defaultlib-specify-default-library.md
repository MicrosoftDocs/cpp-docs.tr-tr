---
description: Şu konuda daha fazla bilgi edinin:/DEFAULTLıB (varsayılan kitaplığı belirt)
title: /DEFAULTLIB (Varsayılan Kitaplığı Belirt)
ms.date: 05/29/2018
f1_keywords:
- VC.Project.VCLinkerTool.DefaultLibraries
- /defaultlib
helpviewer_keywords:
- -DEFAULTLIB linker option
- DEFAULTLIB linker option
- /DEFAULTLIB linker option
- libraries, adding to list of
ms.assetid: 6af7ff49-c170-4a13-97e2-2b9ae2de20c9
ms.openlocfilehash: 9abaf158ed01b3e0a04d29c55d213c8749462c43
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201696"
---
# <a name="defaultlib-specify-default-library"></a>/DEFAULTLIB (Varsayılan Kitaplığı Belirt)

Dış başvuruları çözümlemek için aramak üzere bir varsayılan kitaplık belirtin.

## <a name="syntax"></a>Syntax

> **/Defaultlib**:_kitaplık_

### <a name="arguments"></a>Arguments

*Kitaplığı*<br/>
Dış başvurular çözümlenirken aranacak kitaplığın adı.

## <a name="remarks"></a>Açıklamalar

**/Defaultlib** seçeneği, BAŞVURULARı çözümlerken bağlantıları bağlayan kitaplıklar listesine bir *kitaplık* ekler. **/Defaultlib** ile belirtilen bir kitaplık, komut satırında ve. obj dosyalarında adı geçen varsayılan kitaplıklarla önce açık olarak belirtilen kitaplıkların ardından aranır.

Bağımsız değişkenler olmadan kullanıldığında, [/nodefaultlib (tüm varsayılan kitaplıkları Yoksay)](nodefaultlib-ignore-libraries.md) seçeneği tüm **/defaultlib**:*Library* seçeneklerini geçersiz kılar. **/NODEFAULTLIB**:*Library* seçeneği her ikisinde de aynı *kitaplık* adı belirtildiğinde **/defaultlib**:*Library* geçersiz kılar.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de, her bir kitaplığın aranacağı bir **/defaultlib**:*Library* seçeneği girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC bağlayıcı seçenekleri](linker-options.md)
