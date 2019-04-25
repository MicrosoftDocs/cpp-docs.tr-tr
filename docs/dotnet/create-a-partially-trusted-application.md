---
title: 'Nasıl yapılır: Kısmen güvenilir uygulama oluşturma (C++/CLI)'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- partially trusted applications [C++]
- mixed assemblies [C++], partially trusted applications
- msvcm90[d].dll
- interoperability [C++], partially trusted applications
- interop [C++], partially trusted applications
- /clr compiler option [C++], partially trusted applications
ms.assetid: 4760cd0c-4227-4f23-a7fb-d25b51bf246e
ms.openlocfilehash: afdfb8ca11753d7def9d7da6f431082b1a90c345
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209128"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Nasıl yapılır: CRT kitaplık DLL'İNDEN bağımlılık kaldırarak kısmen güvenilir uygulama oluşturma

Bu konu, msvcm90.dll bağımlılık kaldırarak, Visual C++ kullanarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulacağını açıklar.

İle derlenmiş bir Visual C++ uygulaması **/CLR** C çalışma zamanı kitaplığının parçası olan msvcm90.dll üzerinde bağımlılığa sahip. Kısmi güven ortamında kullanılacak, uygulamanızın istediğinizde, CLR DLL'niz belirli kod erişim güvenlik kurallarında zorlar. Bu nedenle, yerel kod msvcm90.dll içerir ve kod erişimi güvenlik ilkesi üzerinde zorlanamaz çünkü bu bağımlılığı kaldırmak gerekli olacaktır.

Uygulamanız C çalışma zamanı kitaplığı işlevleri kullanmaz ve kodunuzdan bu kitaplığı bağımlılığı kaldırmak istiyor musunuz, kullanması gerekir **/NODEFAULTLIB:msvcmrt.lib** bağlayıcı seçeneği ve bağlantı ptrustm.lib veya ptrustmd.lib. Bu kitaplıklar başlatma ve başlatmayı geri almayı bir uygulamanın nesne dosyalarını içeren, özel durum sınıfları başlatma kodu tarafından kullanılan ve yönetilen özel durum işleme kodu. Bu kitaplıklar birinde bağlama msvcm90.dll herhangi bir bağımlılığı kaldırır.

> [!NOTE]
>  Derleme başlatmasını geri sırasını ptrust kitaplıklarını kullanan uygulamalar için farklı olabilir. Normal uygulamalar için derlemeler yüklü olan, ancak bu garanti edilmez ters sırada genellikle kaldırılır. Kısmi güven uygulamaları için derlemeler genellikle yüklendikleri sırada kaldırılır. Bu, ayrıca, garanti edilmez.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Kısmen güvenilen oluşturmak için karma (/ clr) uygulama

1. Msvcm90.dll bağımlılığı kaldırmak için bu kitaplığı kullanarak içermeyecek şekilde bağlayıcıya belirtmelisiniz **/NODEFAULTLIB:msvcmrt.lib** bağlayıcı seçeneği. Visual Studio geliştirme ortamını kullanarak bunu veya programlamayla, hakkında bilgi için [/nodefaultlıb (kitaplıkları yoksay)](../build/reference/nodefaultlib-ignore-libraries.md).

1. Ptrustm kitaplıklarından birini bağlayıcı giriş bağımlılıkları ekleyin. Uygulamanızın yayın modunda oluşturuyorsanız ptrustm.lib kullanın. Hata ayıklama modu için ptrustmd.lib kullanın. Visual Studio geliştirme ortamını kullanarak bunu veya programlamayla, hakkında bilgi için [. Bağlayıcı girişi dosyaları lib](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Karışık Derlemeleri Başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Karışık Derlemeler için Kitaplık Desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (Seçenekleri Bağlayıcıya Geçir)](../build/reference/link-pass-options-to-linker.md)
