---
title: /ZC:throwingNew (varsay yeni işlecinin)
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
ms.openlocfilehash: 782cb55d30bfb11f55a0074a5c3245dd389323ed
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561232"
---
# <a name="zcthrowingnew-assume-operator-new-throws"></a>/ZC:throwingNew (varsay yeni işlecinin)

Zaman **/Zc:throwingNew** seçeneği belirtildiğinde, derleyici çağrıları iyileştirir `operator new` dönüş null işaretçisi denetimlerini atlamak için. Bu seçenek, tüm uygulamaları bağlı varsaymasını söyler `operator new` ve özel ayırıcılar C++ standardına uygun ve throw ayırma hatası. Visual Studio'da varsayılan olarak, derleyici zor null denetimleri oluşturur. (**/Zc:throwingNew-**) için bu çağırır, kullanıcıların bir oluşturmayan uygulamasıyla bağlayabilirsiniz çünkü `operator new` veya özel bellek ayırıcısı rutinleri yazma Bu, null işaretçi döndürür.

## <a name="syntax"></a>Sözdizimi

> **/ZC:throwingNew**[**-**]

## <a name="remarks"></a>Açıklamalar

ISO C ++ 98 bu yana, standart belirttiği varsayılan [new işleci](../../standard-library/new-operators.md#op_new) oluşturur `std::bad_alloc` bellek ayırma başarısız olduğunda. Visual Studio 6.0 kadar Visual C++ sürümü null bir işaretçi üzerinde bir ayırma hatası döndürdü. Visual Studio 2002'den itibaren `operator new` standartlarına uyar ve hata durumunda oluşturur. Eski ayırma stili kullanan kodu desteklemek için Visual Studio değişkenlerinden bir uygulamasını sağlar `operator new` hatasında bir null işaretçi döndüren nothrownew.obj içinde. Varsayılan olarak, derleyici bu eski stilde ayırıcılar hata durumunda anında bir kilitlenme neden olmasını önlemek için savunma null denetimleri de oluşturur. **/Zc:throwingNew** seçeneği bu null denetimlerinin bırakmak için derleyiciye, tüm bağlı bellek varsayımına ayırıcılar standarda. Bu açık oluşturmayan için uygulanmaz `operator new` ek bir parametre türü kullanılarak bildirilen aşırı yüklemeler `std::nothrow_t` ve açık bir `noexcept` belirtimi.

Kavramsal olarak, ücretsiz mağaza bir nesne oluşturmak için derleyici, bellek ayırmak için kod oluşturur ve sonra bellek başlatmak için bir oluşturucuyu çağırmak için. Visual C++ Derleyici, normalde bu kod için DSCP, oluşturmayan bir ayırıcı bağlı değilse bildiremez olduğundan, varsayılan olarak ayrıca Oluşturucu çağırmadan önce bir null denetimi oluşturur. Bu, bir null işaretçi engeller oluşturmayan bir ayırma başarısız olursa oluşturucu çağrısı başvuru. Çoğu durumda, bu denetimler, gereksiz olduğundan varsayılan `operator new` ayırıcılar throw null karmaşık işaretçilere döndürmek yerine. Denetimleri talihsiz yan etkileri de var. Bunlar kod boyutunu Şişirme, bunlar dal tahmin unsuru doldurmak ve bunlar devirtualization veya const yayma başlatılan nesne dışında gibi diğer yararlı derleyici iyileştirmeleri engelle. Denetimleri bağlanan destek kodu mevcut *nothrownew.obj* veya özel DSCP `operator new` uygulamaları. DSCP kullanmazsanız `operator new`, kullanmanızı öneririz **/Zc:throwingNew** kodunuzu en iyi duruma getirme.

**/Zc:throwingNew** seçeneği varsayılan olarak kapalıdır ve etkilenmez [/ permissive-](permissive-standards-conformance.md) seçeneği.

Bağlama sırasında kod oluşturma (LTCG) kullanarak derleme yaparsanız, belirtmeniz gerekmez **/Zc:throwingNew**. Kodunuz, LTCG kullanılarak derlendiğinde, derleyici algılayabilir varsayılan olarak, uygun `operator new` uygulaması kullanılır. Bu durumda, derleyici null denetimlerinin otomatik olarak bırakır. Bağlayıcı arar **/ThrowingNew** bildirmek için bayrağı, uygulanması `operator new` uygun olan. Bu bayrak bağlayıcıya özel işleç yeni uygulamanız için kaynak bu yönerge dahil ederek belirtebilirsiniz:

```cpp
#pragma comment(linker, "/ThrowingNew")
```

Visual C++'ta uyumluluk sorunları hakkında daha fazla bilgi için bkz: [standart dışı davranış](../../cpp/nonstandard-behavior.md).

## <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Bu derleyici seçeneğini Visual Studio geliştirme ortamında ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Gelen **yapılandırma** açılır menü öğesini **yapılandırmalarında**.

1. Seçin **yapılandırma özellikleri** > **C/C++** > **komut satırı** özellik sayfası.

1. Değiştirme **ek seçenekler** eklenecek özellik **/Zc:throwingNew** veya **/Zc:throwingNew-** seçip **Tamam**.

## <a name="see-also"></a>Ayrıca bkz.

[Derleyici Seçenekleri](../../build/reference/compiler-options.md)<br/>
[Derleyici Seçeneklerini Ayarlama](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (Uyumluluk)](../../build/reference/zc-conformance.md)<br/>
[noexcept (C++)](../../cpp/noexcept-cpp.md)<br/>
[Özel Durum Belirtimleri (throw) (C++)](../../cpp/exception-specifications-throw-cpp.md)<br/>
[Sonlandır (özel durum)](../../standard-library/exception-functions.md#terminate)<br/>
