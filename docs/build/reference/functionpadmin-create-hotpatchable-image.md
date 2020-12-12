---
description: Daha fazla bilgi edinin:/FUNCTIONPADMIN (düzeltme eki uygulanmış görüntü oluşturma)
title: /FUNCTIONPADMIN (Düzeltme Eki Eklenebilen Görüntü Oluşturma)
ms.date: 03/09/2018
f1_keywords:
- /functionpadmin
helpviewer_keywords:
- -FUNCTIONPADMIN linker option
- /FUNCTIONPADMIN linker option
ms.assetid: 25b02c13-1add-4fbd-add9-fcb30eb2cae7
ms.openlocfilehash: f86adb2001adacf1b6c8a03a90b7452505841c08
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192011"
---
# <a name="functionpadmin-create-hotpatchable-image"></a>/FUNCTIONPADMIN (Düzeltme Eki Eklenebilen Görüntü Oluşturma)

Anında düzeltme için bir görüntü hazırlar.

## <a name="syntax"></a>Syntax

> **/Functionpadmin**[**:**_Space_]

### <a name="arguments"></a>Arguments

*space*<br/>
Her bir işlevin başına bayt olarak eklenecek doldurma miktarı. X86 üzerinde bu, varsayılan olarak 5 baytlık doldurma ve x64 üzerinde varsayılan 6 bayttır. Diğer hedeflerde bir değer sağlanmalıdır.

## <a name="remarks"></a>Açıklamalar

Bağlayıcının hotpatch bir görüntü oluşturması için. obj dosyaları [/hotpatch (düzeltme eki eklenmiş görüntü oluştur)](hotpatch-create-hotpatchable-image.md)ile derlenmiş olmalıdır.

cl.exe tek bir Çağrılı bir görüntüyü derleyip bağladığınızda **/hotpatch** **/FUNCTIONPADMIN**' i belirtir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **komut satırı** özellik sayfasını seçin.

1. **Ek seçenekler**' de **/functionpadmin** seçeneğini girin. Değişikliklerinizi kaydetmek için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
