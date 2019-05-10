---
title: DLL Türleri
ms.date: 05/06/2019
helpviewer_keywords:
- MFC DLLs [C++], types
- DLLs [C++], types
- DLLs [C++], MFC
ms.assetid: f6a30db9-6138-4b2c-90cc-a17855e499a6
ms.openlocfilehash: 9e66fa1c24ea00961d99eef02c15526eff4eb533
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221480"
---
# <a name="kinds-of-dlls"></a>DLL Türleri

Bu konu, oluşturacağınız DLL'nin türünü belirlemenize yardımcı olacak bilgiler sağlar.

##  <a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a> Farklı türdeki kullanılabilir DLL'ler

Visual Studio kullanarak, C'de Win32 DLL'leri oluşturabilirsiniz veya C++ Microsoft Foundation Class (MFC) kitaplığı kullanmayın. Win32 Uygulama Sihirbazı ile MFC DLL projesi oluşturabilirsiniz.

MFC Kitaplığı hem statik bağlantı kitaplıklarında veya bir bazı DLL'lerde MFC DLL Sihirbazı ile kullanılabilir. DLL'niz MFC kullanıyorsa, Visual Studio üç farklı DLL geliştirme senaryosu destekler:

- Statik bir Normal MFC DLL oluşturma

- Dinamik olarak Normal MFC DLL oluşturma

- Bir MFC uzantılı DLL oluşturma, her zaman dinamik olarak MFC'ye

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantısı DLL’leri: Genel Bakış](extension-dlls-overview.md)

- [Hangi tür DLL kullanılacak?](#_core_which_kind_of_dll_to_use)

##  <a name="_core_which_kind_of_dll_to_use"></a> Hangi tür DLL kullanılacağına karar verme

DLL'niz MFC kullanmıyorsa, bir MFC olmayan Win32 DLL oluşturmak için Visual Studio'yu kullanın. (Statik veya dinamik olarak) DLL'nizi MFC'ye bağlama, önemli ölçüde disk alanını ve belleği doldurur. Aslında DLL dosyanız bir MFC kullanmadığı sürece MFC'ye bağlantı yapmamanız gerekir.

DLL'niz MFC kullanacaksa ve MFC veya MFC olmayan uygulamalar tarafından kullanılan, dinamik olarak MFC'ye bağlanan normal bir MFC DLL veya statik olarak MFC'ye bağlı normal MFC DLL'SİNİN oluşturmanız gerekir. Çoğu durumda, büyük olasılıkla, DLL dosyanızın boyutu daha küçük olacağından ve tasarruf kullanarak MFC'nin paylaşılan sürümünden belleğe yapılan kayıtlar önemli olabileceğinden MFC'ye dinamik olarak bağlanan normal MFC DLL'SİNİN kullanmak istediğiniz. MFC'ye statik olarak bağlarsanız, DLL dosyanızın boyutu daha büyük ve fazla bellek alanı dolduracaktır, kendi özel MFC kitaplık kodu kopyasını yüklediğinden potansiyel olarak alın.

MFC'ye dinamik olarak bir DLL derlenirken MFC'nin kendisine bağlamak gerekli olduğundan, statik olarak MFC'ye bağlı bir DLL'yi oluşturmaktan daha hızlıdır. Bu, özellikle nerede bağlayıcı hata ayıklama bilgilerini sıkıştırmasının gerektiği hata ayıklama yapılarında doğrudur. Hata ayıklama bilgilerini önceden içeren bir DLL'ye, DLL dosyanız içinde sıkıştırmak için daha az hata ayıklama bilgileri yoktur.

MFC'ye dinamik olarak bağlama bir dezavantajı, paylaşılan dll Mfcx0.dll ve Msvcrxx.dll (veya benzer dosyaları) DLL ile dağıtmanız ' dir. MFC DLL'leri ücretsiz olarak yeniden dağıtılabilir, ancak yine de DLL'leri Kurulum programınıza yüklemelisiniz. Ayrıca, programınız ve MFC DLL'lerinin kendilerinin kullanılan C çalışma zamanı kitaplığı içeren Msvcrxx.dll hazırlamalısınız.

DLL'niz yalnızca MFC yürütülebilir dosyaları tarafından kullanılacaksa, Normal MFC DLL'SİNİN veya bir MFC uzantılı DLL oluşturma arasında seçim sahip. DLL'niz varolan MFC sınıflarından türetilmiş yeniden kullanılabilir sınıfları tümleştirirse veya uygulama ve DLL arasında MFC'den türetilmiş nesneler geçirmek istiyorsanız, bir MFC uzantılı DLL oluşturmanız gerekir.

DLL'nizi MFC'ye, MFC DLL'leri DLL'niz ile yeniden dağıtılabilir. Bu mimari, disk alanından tasarruf etmek ve bellek kullanımını en aza indirmek için birden fazla yürütülebilir dosya arasında sınıf kitaplığının paylaşımı için özellikle yararlıdır.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla bilgi edinmek istiyorsunuz?

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantısı DLL’leri: Genel Bakış](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C/C++ DLL'leri oluşturma](dlls-in-visual-cpp.md)
