---
title: 'Nasıl Yapılır: Kısmen Güvenilen Bir Uygulama Oluşturma (C++/CLI)'
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
ms.openlocfilehash: 9df3a751f4073472b9495425599aaf43878db99a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364399"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Nasıl yapılır: CRT Kitaplık DLL'inden Bağımlılık Kaldırarak Kısmen Güvenilir Uygulama Oluşturma

Bu konu, msvcm90.dll bağımlılığını kaldırarak Visual C++ kullanarak kısmen güvenilen bir Ortak Dil Çalışma Zamanı uygulamasının nasıl oluşturulacağını tartışır.

**/clr** ile oluşturulmuş bir Visual C++ uygulaması, C-Runtime Kitaplığı'nın bir parçası olan msvcm90.dll'ye bağımlı olacaktır. Uygulamanızın kısmi bir güven ortamında kullanılmasını istediğinizde, CLR DLL'nizde belirli kod erişim güvenlik kurallarını uygular. Bu nedenle, msvcm90.dll yerel kod içerdiğinden ve kod erişim güvenlik ilkesi üzerinde uygulanamaz, çünkü bu bağımlılığı kaldırmak için gerekli olacaktır.

Uygulamanız C-Runtime Kitaplığı'nın herhangi bir işlevini kullanmıyorsa ve bu kitapletmeye olan bağımlılığı kodunuzdan kaldırmak istiyorsanız, **/NODEFAULTLIB:msvcmrt.lib** bağlayıcı seçeneğini ve ptrustm.lib veya ptrustmd.lib bağlantılarını kullanmanız gerekir. Bu kitaplıklar, bir uygulamanın başlatılması ve başlatılması için nesne dosyaları, başlatma kodu tarafından kullanılan özel durum sınıfları ve yönetilen özel durum işleme kodu içerir. Bu kitaplıklardan birine bağlanmak msvcm90.dll üzerindeki tüm bağımlılıkları ortadan kaldırır.

> [!NOTE]
> Derleme uninitialization sırası ptrust kitaplıkları kullanan uygulamalar için farklı olabilir. Normal uygulamalar için derlemeler genellikle yüklendikleri ters sırada boşaltılır, ancak bu garanti edilmez. Kısmi güven uygulamaları için derlemeler genellikle yüklendikleri sırada boşaltılır. Bu da garanti edilmez.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Kısmen güvenilen karma (/clr) bir uygulama oluşturmak için

1. msvcm90.dll bağımlılığını kaldırmak için, **/NODEFAULTLIB:msvcmrt.lib** bağlayıcı seçeneğini kullanarak bu kitaplığı eklememek için bağlayıcıya belirtmeniz gerekir. Visual Studio geliştirme ortamını kullanarak veya programlı olarak nasıl yapılacağınız hakkında bilgi [için](../build/reference/nodefaultlib-ignore-libraries.md)bkz.

1. Bağlayıcı giriş bağımlılıklarına ptrustm kitaplıklarından birini ekleyin. Uygulamanızı sürüm modunda oluşturuyorsanız ptrustm.lib'i kullanın. Hata ayıklama modu için ptrustmd.lib kullanın. Visual Studio geliştirme ortamını kullanarak veya programlı olarak bunu nasıl yapacağınız hakkında bilgi için [bkz. Bağlayıcı Girişi olarak Lib Dosyaları](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (Yerel ve Yönetilen) Derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Karışık Derlemeleri Başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Karma Derlemeler için Kütüphane Desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/link (Seçenekleri Bağlayıcıya Geçir)](../build/reference/link-pass-options-to-linker.md)
