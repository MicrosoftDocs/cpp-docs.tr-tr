---
title: / WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)
ms.date: 11/04/2016
ms.assetid: ee92d12f-18af-4602-9683-d6223be62ac9
ms.openlocfilehash: db99816b18110b424647603196040997044e7fbd
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808657"
---
# <a name="wholearchive-include-all-library-object-files"></a>/ WHOLEARCHIVE (tüm kitaplık nesnesi dosyalarını dahil et)

Bağlantılı yürütülebilir dosya içindeki statik kitaplıkta tüm nesnesi dosyalarını dahil için zorla.

## <a name="syntax"></a>Sözdizimi

> / WHOLEARCHIVE [:*Kitaplığı*]

## <a name="remarks"></a>Açıklamalar

Wholearchıve seçeneği bağlayıcıya her nesne dosyasından ya da belirtilen bir statik kitaplık içeren veya bağlantı için belirtilen tüm statik kitaplıklarından kitaplık belirtilmezse, komut zorlar. Birden çok kitaplık wholearchıve seçeneğini belirtmek için birden fazla wholearchıve geçiş bağlayıcı komut satırına kullanabilirsiniz. Yalnızca diğer nesne dosyaları yürütülebilir dosya tarafından başvurulan sembolleri veriyorsanız varsayılan olarak, bağlı çıktısında nesne dosyalarının bağlayıcı içerir. Tüm nesne dosyaları tek tek bağlayıcı komut satırına belirtikleri gibi statik kitaplıkta bırakılıyorsa kabul bağlayıcı wholearchıve seçenektir.

Wholearchıve seçeneği, statik bir kitaplıktan tüm sembolleri yeniden dışarı aktarmak için kullanılabilir. Bu, birden fazla statik Kitaplığı'ndan bir bileşen oluşturduğunuzda tüm kitaplık kodu, kaynakları ve meta verileri bulunduğundan emin olmanızı sağlar. Windows çalışma zamanı bileşenleri için dışarı aktarma uyarısı statik kitaplık oluşturduğunuzda LNK4264 içeren görürseniz, bu kitaplığın başka bir bileşen ya da uygulama bağlama wholearchıve seçeneği kullanın.

Wholearchıve seçeneği, Visual Studio 2015 güncelleştirme 2'de sunulmuştur.

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio'da bu bağlayıcı seçeneğini ayarlamak için

1. Projeyi açmak **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](../working-with-project-properties.md).

1. Seçin **komut satırı** altında özellik sayfası **yapılandırma özellikleri**, **bağlayıcı**.

1. Wholearchıve seçeneği ekleyin **ek seçenekler** metin kutusu.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
