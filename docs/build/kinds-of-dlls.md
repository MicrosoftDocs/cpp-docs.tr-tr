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

Bu konu, oluşturmak için DLL türünü belirlemenize yardımcı olacak bilgiler sağlar.

## <a name="different-kinds-of-dlls-available"></a><a name="_core_the_different_kinds_of_dlls_available_with_visual_c.2b2b"></a>Farklı DL'ler Mevcut

Visual Studio'yu kullanarak, Microsoft Hazırlık Sınıfı (MFC) kitaplığını kullanmayan C veya C++'da Win32 DL'ler oluşturabilirsiniz. Win32 Uygulama Sihirbazı ile MFC olmayan bir DLL projesi oluşturabilirsiniz.

MFC kitaplığı, statik bağlantı kitaplıklarında veya mfc DLL Sihirbazı ile birlikte birkaç DL'de kullanılabilir. DLL'niz MFC kullanıyorsa, Visual Studio üç farklı DLL geliştirme senaryosudestekler:

- MFC'yi statik olarak birbirine bağlayan normal bir MFC DLL oluşturma

- MFC'yi dinamik olarak birbirine bağlayan normal bir MFC DLL oluşturma

- Her zaman dinamik bağlantı MFC bir MFC uzantısı DLL, bina

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla şey bilmek istiyorsun?

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantı DLL'leri: Genel Bakış](extension-dlls-overview.md)

- [Hangi dll türü kullanmak](#_core_which_kind_of_dll_to_use)

## <a name="deciding-which-kind-of-dll-to-use"></a><a name="_core_which_kind_of_dll_to_use"></a>Hangi DLL Türünü Kullanacağına Karar Verme

DLL'niz MFC kullanmıyorsa, MFC olmayan bir Win32 DLL oluşturmak için Visual Studio'yı kullanın. DLL'nizi MFC'ye bağlamak (statik veya dinamik olarak) önemli disk alanı ve bellek alır. DLL'niz aslında MFC kullanmadığı sürece MFC'ye bağlanmamalısınız.

DLL'niz MFC kullanıyorsa ve MFC olmayan uygulamalar tarafından kullanılacaksa, MFC'ye dinamik olarak bağlanan normal bir MFC DLL veya Statik olarak MFC'ye bağlanan normal bir MFC DLL oluşturmanız gerekir. Çoğu durumda, dll dosya boyutu çok daha küçük olacak ve MFC paylaşılan sürümünü kullanarak bellek tasarrufu önemli olabilir, çünkü büyük olasılıkla mfc dinamik olarak MFC bağlantılar normal bir MFC DLL kullanmak istiyorum. MFC'ye statik olarak bağlanırsanız, DLL'nizin dosya boyutu daha büyük olur ve MFC kitaplık kodunun kendi özel kopyasını yükler diye ek bellek alabilir.

MFC'ye dinamik olarak bağlanan bir DLL oluşturmak, MFC'yi bağlamaya gerek olmadığı için MFC'ye statik olarak bağlanan bir DLL oluşturmaktan daha hızlıdır. Bu, özellikle bağlayıcının hata ayıklama bilgilerini sıkıştırması gereken hata ayıklama yapılarında geçerlidir. Hata ayıklama bilgilerini zaten içeren bir DLL ile bağlantı vererek, DLL'nizde sıkıştırılaması gereken daha az hata ayıklama bilgisi vardır.

MFC'ye dinamik olarak bağlanmanın bir dezavantajı, paylaşılan DL'leri Mfcx0.dll ve Msvcrxx.dll (veya benzer dosyaları) DLL'nizle dağıtmanız gerektiğidir. MFC DL'ler serbestçe dağıtılabilir, ancak yine de kurulum programınızda DL'leri yüklemeniz gerekir. Buna ek olarak, hem programınız hem de MFC DL'lerin kendileri tarafından kullanılan C çalışma zamanı kitaplığını içeren Msvcrxx.dll'yi göndermeniz gerekir.

DLL'niz yalnızca MFC çalıştırılabilir leri tarafından kullanılacaksa, normal bir MFC DLL veya MFC uzantısı DLL oluşturmak arasında bir seçim seçeneğiniz vardır. DLL'niz varolan MFC sınıflarından türetilen yeniden kullanılabilir sınıflar uyguluyorsa veya uygulama ile DLL arasında MFC türetilmiş nesneleri geçirmeniz gerekiyorsa, bir MFC uzantısı DLL oluşturmanız gerekir.

DLL'niz MFC'ye dinamik olarak bağlanırsa, MFC DLL'leriniz DLL'niz ile yeniden dağıtılabilir. Bu mimari, disk alanı kaydetmek ve bellek kullanımını en aza indirmek için sınıf kitaplığını birden çok yürütülebilir dosya arasında paylaşmak için özellikle yararlıdır.

### <a name="what-do-you-want-to-know-more-about"></a>Ne hakkında daha fazla şey bilmek istiyorsun?

- [MFC Dışı DLL'ler: Genel Bakış](non-mfc-dlls-overview.md)

- [Statik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-statically-linked-to-mfc.md)

- [Dinamik olarak MFC'ye bağlı normal MFC DLL'leri](regular-dlls-dynamically-linked-to-mfc.md)

- [MFC uzantı DLL'leri: Genel Bakış](extension-dlls-overview.md)

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio'da C/C++ DL'ler oluşturma](dlls-in-visual-cpp.md)
