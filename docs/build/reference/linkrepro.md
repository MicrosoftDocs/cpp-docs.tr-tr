---
title: /LINKREPRO (bağlantıyı yeniden üretme dizin adı)
description: Bir bağlantının yeniden üretme dizinini ayarlamak için bağlayıcı veya kitaplık aracı seçeneği.
ms.date: 09/24/2019
f1_keywords:
- /LINKREPRO
helpviewer_keywords:
- LINKREPRO linker option
- /LINKREPRO linker option
- -LINKREPRO linker option
- linker repro reporting
ms.openlocfilehash: d81fb529cdbb0741c6dff58032dad97df89b4d4f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/30/2019
ms.locfileid: "71686854"
---
# <a name="linkrepro-link-repro-directory-name"></a>/LINKREPRO (bağlantıyı yeniden üretme dizin adı)

Bağlayıcı veya kitaplık aracına, belirtilen dizinde bir bağlantı yeniden üretme oluşturmasını söyler.

## <a name="syntax"></a>Sözdizimi

> **/LINKREPRO:** _Dizin-adı_

### <a name="arguments"></a>Bağımsız Değişkenler

**/LINKREPRO:** _dizin-adı_\
Bağlantının yeniden üretilemedi depolanacak Kullanıcı tarafından belirtilen dizin. Boşluk içeren dizin adlarının çift tırnak içine alınması gerekir.

## <a name="remarks"></a>Açıklamalar

**/LINKREPRO** seçeneği, bir *bağlantı yeniden üretme*oluşturmak için kullanılır. Bu, Microsoft 'un bağlantı zamanında veya kitaplık işlemleri sırasında oluşan bir sorunu yeniden üretme olanak tanıyan bir dizi derleme yapıtı. Bağlantı zamanı kod oluşturma (LTCG), LNK1000 bağlayıcı hatası veya bağlayıcı kilitlenmesiyle ilgili arka uç kilitlenmesi gibi sorunlar için faydalıdır. Araç, **/LINKREPRO** bağlayıcı seçeneğini belirttiğinizde veya komut satırı yapı ortamınızda `link_repro` ortam değişkenini ayarladığınızda bir bağlantı yeniden oluşturma işlemi üretir. Daha fazla bilgi için, [Microsoft C++ araç takımı ile sorun bildirme](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md)konusunun [reprofesyonelleri bağlantısını](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md#link-repros) inceleyin.

Hem **/LINKREPRO** bağlayıcı seçeneği hem de `link_repro` ortam değişkeni, bağlantının yeniden üretme için bir çıkış dizini belirtmenizi gerektirir. Komut satırında veya IDE 'de, **/LINKREPRO:** _Directory-Name_ seçeneğini kullanarak dizini belirtin. Belirttiğiniz _Dizin adı_ mutlak veya göreli bir yol olabilir, ancak dizin var olmalıdır. Komut satırı seçeneği `link_repro` ortam değişkeninde ayarlanan tüm dizin değerlerini geçersiz kılar.

Bağlantı yeniden üretme üretimini belirli bir hedef dosya adına sınırlama hakkında daha fazla bilgi için [/LINKREPROTARGET](linkreprotarget.md) seçeneğine bakın. Bu seçenek, için bir bağlantı yeniden üretme oluşturmak üzere belirli bir hedef belirtmek için kullanılabilir. Bağlayıcı veya kitaplık aracını birden çok kez çağıran karmaşık derlemelerde yararlıdır.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamında bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual C++ Studio 'da derleyici ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri** > **bağlayıcı** > **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** kutusuna **/LINKREPRO:** _Directory-Name_ seçeneğini girin. Belirttiğiniz _Dizin adı_ değeri var olmalıdır. Değişikliği uygulamak için **Tamam ' ı** seçin.

Bağlantıyı yeniden üretme oluşturduktan sonra, **/LINKREPRO** seçeneğini derlemelerinizi kaldırmak için bu özellik sayfasını tekrar açın.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

- @No__t-0 ' a bakın.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)\
[/LINKREPROTARGET](linkreprotarget.md)
