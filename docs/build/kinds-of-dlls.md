---
title: DLL Türleri
ms.date: 05/06/2019
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
ms.openlocfilehash: dae44d2dd39597420ce2a2c4e1642e8a7f0784e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81328496"
---
# <a name="kinds-of-dlls"></a>DLL Türleri

Bu konu, Derlenecek DLL türünü belirlemenize yardımcı olacak bilgiler sağlar.

## <a name="different-kinds-of-dlls-available"></a><a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a>Farklı DLL türleri var

Visual Studio 'yu kullanarak, C veya C++ ' da Microsoft Foundation Class (MFC) kitaplığı kullanmayan Win32 DLL 'Ler oluşturabilirsiniz. Win32 uygulama Sihirbazı ile MFC olmayan bir DLL projesi oluşturabilirsiniz.

MFC kitaplığı, MFC DLL Sihirbazı ile statik bağlantı kitaplıklarında veya bir dizi dll 'de kullanılabilir. DLL 'niz MFC kullanıyorsa, Visual Studio üç farklı DLL geliştirme senaryosunu destekler:

- MFC 'ye statik olarak bağlanan normal bir MFC DLL oluşturma

- MFC 'ye dinamik olarak bağlanan normal bir MFC DLL oluşturma

- MFC 'yi her zaman dinamik olarak bağlayan MFC uzantı DLL 'SI oluşturma

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantı DLL'leri: Genel Bakış](extension-dlls-overview.md)

- [Kullanılacak DLL türü](#_core_which_kind_of_dll_to_use)

## <a name="deciding-which-kind-of-dll-to-use"></a><a name="_core_which_kind_of_dll_to_use"></a>Hangi tür DLL 'nin kullanılması gerektiğine karar verme

DLL 'niz MFC kullanmıyorsa, MFC olmayan bir Win32 DLL oluşturmak için Visual Studio 'Yu kullanın. DLL 'nizi MFC 'ye bağlama (statik veya dinamik olarak) önemli disk alanı ve bellek kaplar. DLL 'niz gerçekten MFC kullanmadığı takdirde MFC 'ye bağlanmamalıdır.

DLL 'niz MFC kullanıyorsa ve MFC ya da MFC olmayan uygulamalar tarafından kullanılacaksa, MFC 'ye dinamik olarak bağlanan normal bir MFC DLL veya MFC 'ye statik olarak bağlanan normal bir MFC DLL derlemeniz gerekir. Çoğu durumda, DLL 'nin dosya boyutu çok daha küçük olacağından ve MFC 'nin paylaşılan sürümünü kullanarak bellek tasarrufları önemli olabileceğinden, büyük olasılıkla MFC 'ye dinamik olarak bağlanan normal bir MFC DLL kullanmak istersiniz. MFC 'ye statik olarak bağlantı oluşturduysanız, DLL 'nizin dosya boyutu daha büyük olur ve büyük olasılıkla MFC kitaplık kodunun özel bir kopyasını yüklediği için daha fazla bellek alabilir.

MFC 'ye dinamik olarak bağlanan bir DLL oluşturma, MFC 'nin kendisini bağlamak gerekli olmadığından, MFC 'ye statik olarak bağlanan bir DLL oluşturma özelliğinden daha hızlıdır. Bu, bağlayıcının hata ayıklama bilgilerini sıkıştıracağı hata ayıklama yapılarında de geçerlidir. Hata ayıklama bilgilerini zaten içeren bir DLL ile bağlantı kurarak, DLL 'niz içinde sıkıştırmak için daha az hata ayıklama bilgisi vardır.

MFC 'ye dinamik olarak bağlanmanın bir dezavantajı, MFCx0. dll ve Msvcrxx. dll paylaşılan DLL 'Lerini (veya benzer dosyaları) DLL 'iyle dağıtmanız gerekir. MFC DLL 'Leri serbestçe yeniden dağıtılabilir, ancak yine de dll 'Leri kurulum programınızdaki yükleme yapmanız gerekir. Ayrıca, hem programınız hem de MFC DLL 'Leri tarafından kullanılan C çalışma zamanı kitaplığını içeren Msvcrxx. dll dosyasını teslim etmeniz gerekir.

DLL 'niz yalnızca MFC yürütülebilir dosyaları tarafından kullanılacaksa, normal MFC DLL veya MFC uzantısı DLL 'SI oluşturma arasında seçim yapabilirsiniz. DLL 'niz var olan MFC sınıflarından türetilmiş yeniden kullanılabilir sınıflar uygularsa veya uygulama ile DLL arasında MFC 'den türetilmiş nesneler geçirmeniz gerekiyorsa, bir MFC uzantısı DLL oluşturmanız gerekir.

DLL 'niz MFC 'ye dinamik olarak bağlanıyorsa, MFC DLL 'Leri DLL 'niz ile yeniden dağıtılabilir. Bu mimari, disk alanından tasarruf etmek ve bellek kullanımını en aza indirmek için birden fazla yürütülebilir dosya arasında sınıf kitaplığını paylaştırmak için özellikle yararlıdır.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantı DLL'leri: Genel Bakış](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio 'da C/C++ dll 'Leri oluşturma](dlls-in-visual-cpp.md)
