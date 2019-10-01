---
title: /LINKREPROTARGET (bağlantıyı yeniden üretme dosya adı)
description: Bağlantı yeniden üretme için bir hedef dosya adı ayarlamak için bağlayıcı veya kitaplık aracı seçeneği.
ms.date: 09/24/2019
f1_keywords:
- /LINKREPROTARGET
helpviewer_keywords:
- LINKREPROTARGET linker option
- /LINKREPROTARGET linker option
- -LINKREPROTARGET linker option
- linker repro reporting
ms.openlocfilehash: 4912e8bc64d31e3ecc97ea25783c7329e7d7861c
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686840"
---
# <a name="linkreprotarget-link-repro-file-name"></a>/LINKREPROTARGET (bağlantıyı yeniden üretme dosya adı)

Bağlayıcı veya kitaplık aracına yalnızca hedef belirtilen dosya adına sahip olduğunda bir bağlantı yeniden üretme oluşturmasını söyler.

## <a name="syntax"></a>Sözdizimi

> **/LINKREPROTARGET:** _dosya adı_

### <a name="arguments"></a>Bağımsız Değişkenler

**/LINKREPROTARGET:** _dosya adı_\
Filtrelenecek hedef dosya adı. Bağlantı yeniden üretme yalnızca, adlandırılmış dosya çıkış hedefi olduğunda oluşturulur. Boşluk içeren dosya adları çift tırnak içine alınmalıdır. Dosya adı, temel adı ve uzantıyı içermelidir, ancak yolu içermemelidir.

## <a name="remarks"></a>Açıklamalar

**/LINKREPROTARGET** seçeneği, için bir *bağlantı yeniden üretme* oluşturmak üzere bir hedef dosya adı belirtmek için kullanılır. Bağlantı yeniden üretme, Microsoft 'un bağlantı zamanında veya kitaplık işlemleri sırasında oluşan bir sorunu yeniden üretme izni veren bir yapı yapıtı kümesidir. Bağlayıcı veya kitaplık Aracı, [/LINKREPRO](linkrepro.md) seçeneğini belirttiğinizde veya komut satırı yapı ortamınızda `link_repro` ortam değişkenini ayarladığınızda bir bağlantı yeniden oluşturma işlemi üretir.

**/LINKREPROTARGET** seçeneği, bağlayıcı veya kitaplık aracını birden çok kez çağıran karmaşık derlemelerde yararlıdır. Bağlantı yeniden üretme için, *sorun. dll*gibi belirli bir hedef belirtmenize olanak tanır. Yalnızca araç belirli bir dosya ürettiğinden bağlantıyı yeniden oluşturmayı oluşturmanızı sağlar.

Bağlantı yeniden oluşturmanın nasıl ve ne zaman oluşturulacağı hakkında daha fazla bilgi için, [Microsoft C++ araç takımı ile sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)konusunun [reprofesyonelleri bağlantısını](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md#link-repros) inceleyin.

**/LINKREPROTARGET** seçeneğinin herhangi bir etkisi olması için **/LINKREPRO** ve [/Out](out-output-file-name.md) seçeneklerinin ayarlanmış olması gerekir.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/LINKREPROTARGET:** _File-Name_ seçeneğini girin. Değişikliği uygulamak için **Tamam ' ı** seçin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- @No__t-0 ' a bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)\
[/LINKREPRO](linkrepro.md)
