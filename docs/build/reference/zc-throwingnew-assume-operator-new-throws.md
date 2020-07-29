---
title: /Zc:throwingNew (Yeni işlecinin oluşturacağını varsay)
ms.date: 03/01/2018
f1_keywords:
- throwingNew
- /Zc:throwingNew
helpviewer_keywords:
- -Zc compiler options (C++)
- throwingNew
- Assume operator new Throws
- /Zc compiler options (C++)
- Zc compiler options (C++)
ms.assetid: 20ff0101-9677-4d83-8c7b-8ec9ca49f04f
ms.openlocfilehash: 7593107a280995145d252efa76e0a88bddbd2275
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211872"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/Zc:throwingNew (Yeni işlecinin oluşturacağını varsay)

**/Zc: throwingNew** seçeneği belirtildiğinde, derleyici `operator new` bir null işaretçi dönüşü için denetimleri atlamak üzere öğesine çağrıları iyileştirir. Bu seçenek derleyicinin tüm bağlantılı uygulamalarının `operator new` ve özel ayırıcıların C++ standardına uygun olduğunu varsaymasını ve ayırma hatası üzerine atmasını söyler. Visual Studio 'da varsayılan olarak, derleyici pessimistically, bu çağrılar için null denetimler (**/Zc: throwingNew-**) oluşturur, çünkü kullanıcılar, `operator new` null işaretçiler döndüren özel ayırıcı yordamları veya yazmasız bir uygulamayla bağlantı oluşturabilir.

## <a name="syntax"></a>Sözdizimi

> **/Zc: throwingNew**[ **-** ]

## <a name="remarks"></a>Açıklamalar

ISO C++ 98 ' den itibaren, standart, bellek ayırma başarısız olduğunda yeni varsayılan [işlecinin](../../standard-library/new-operators.md#op_new) bulunduğunu belirtti `std::bad_alloc` . Visual Studio 6,0 ' ye kadar Visual C++ sürümleri, ayırma hatasında null bir işaretçi döndürdü. Visual Studio 2002 ' den başlayarak, `operator new` standarda uygun ve hata üzerine oluşturur. Daha eski ayırma stilini kullanan kodu desteklemek için Visual Studio, `operator new` hata durumunda null bir işaretçi döndüren nothrownew. obj içinde yerleşik bir uygulama sağlar. Varsayılan olarak, derleyici, bu eski stil ayırıcıların hata durumunda anında kilitlenmeye neden olmasına engel olmak için savunma null denetimleri de oluşturur. **/Zc: throwingNew** seçeneği, derleyicinin bu null denetimleri, tüm bağlantılı bellek ayırıcıların standart ile uyumlu olduğunu varsayımına göre bırakmasını söyler. Bu `operator new` , türü ek bir parametre kullanılarak tanımlanan `std::nothrow_t` ve açık bir belirtim içeren açık bir atma olmayan aşırı yüklemeler için geçerlidir **`noexcept`** .

Kavramsal olarak, ücretsiz depoda bir nesne oluşturmak için derleyici, belleğini ayırmak üzere kod oluşturur ve sonra belleği başlatmak için oluşturucusunu çağırır. MSVC derleyicisi normal olarak bu kodun uyumsuz, oluşturma olmayan bir ayırıcıyla bağlantılı olup olmadığını söylemediğinden, Oluşturucu çağrılmadan önce de null denetimi oluşturur. Bu, bir atma işlemi olmayan bir ayırma başarısız olursa, Oluşturucu çağrısında null işaretçi başvurusu yapılmasını önler. Çoğu durumda bu denetimler gereksizdir, çünkü varsayılan `operator new` ayrıcılar null işaretçiler döndürmek yerine oluşturulur. Denetimlerin Ayrıca talihsiz yan etkileri de vardır. Kod boyutunu bloonlar, dal tahminlerinin dışına taşırlar ve başlatılan nesneden devirtualization ya da const yayma gibi diğer yararlı derleyici iyileştirmelerini öngörür. Denetimler yalnızca *nothrownew. obj* öğesine bağlanan veya özel bir uyumsuz uygulamalara sahip olan kodu destekler `operator new` . Uyumlu olmayan kullanmıyorsanız `operator new` , kodunuzu iyileştirmek için **/Zc: throwingNew** kullanmanızı öneririz.

**/Zc: throwingNew** seçeneği varsayılan olarak kapalıdır ve [/Permissive-](permissive-standards-conformance.md) seçeneğinden etkilenmez.

Bağlantı zamanı kod oluşturma (LTCG) kullanarak derlerseniz, **/Zc: throwingNew**belirtmeniz gerekmez. Kodunuz LTCG kullanılarak derlenirse, derleyici varsayılan, uyumlu `operator new` uygulamanın kullanıldığını algılayabilir. Bu durumda, derleyici null denetimleri otomatik olarak bırakır. Bağlayıcı, uygulamasının uygulamanın uyumlu olup olmadığını söylemek için **/ThrowingNew** bayrağını arar `operator new` . Özel operatör yeni uygulamanız için bu yönergeyi kaynağa ekleyerek bağlayıcıya bu bayrağı belirtebilirsiniz:

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Visual C++ uyumluluk sorunları hakkında daha fazla bilgi için bkz. [Standart olmayan davranış](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma** açılan menüsünde **tüm yapılandırmalar**' ı seçin.

1. **Yapılandırma özellikleri**  >  **C/C++**  >  **komut satırı** Özellik sayfası ' nı seçin.

1. **Ek seçenekler** özelliğini **/Zc: throwingNew** veya **/Zc: throwingNew** içerecek şekilde değiştirin ve ardından **Tamam**' ı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC derleyici seçenekleri](compiler-options.md)<br/>
[MSVC derleyici komut satırı sözdizimi](compiler-command-line-syntax.md)<br/>
[/Zc (Uyumluluk)](zc-conformance.md)<br/>
[noexcept (C++)](../../cpp/noexcept-cpp.md)<br/>
[Özel Durum Belirtimleri (throw) (C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[Sonlandır (özel durum)](../../standard-library/exception-functions.md#terminate)<br/>
