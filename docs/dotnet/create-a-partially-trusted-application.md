---
description: "Daha fazla bilgi edinin: nasıl yapılır: CRT kitaplık DLL 'inin bağımlılığını kaldırarak kısmen güvenilir uygulama oluşturma"
title: 'Nasıl yapılır: kısmen güvenilen bir uygulama oluşturma (C++/CLı)'
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
ms.openlocfilehash: 937262595df4415d5620b60d9ccd8c17a6c44abf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124286"
---
# <a name="how-to-create-a-partially-trusted-application-by-removing-dependency-on-the-crt-library-dll"></a>Nasıl yapılır: CRT Kitaplık DLL'inden Bağımlılık Kaldırarak Kısmen Güvenilir Uygulama Oluşturma

Bu konuda, msvcm90.dll bağımlılığı kaldırılarak Visual C++ kullanılarak kısmen güvenilir bir ortak dil çalışma zamanı uygulamasının nasıl oluşturulacağı açıklanmaktadır.

**/Clr** ile derlenen bir Visual C++ uygulaması, C çalışma zamanı kitaplığının bir parçası olan msvcm90.dll bir bağımlılığa sahip olur. Uygulamanızın kısmi güven ortamında kullanılmasını istediğinizde, CLR, DLL 'niz üzerinde belirli kod erişimi güvenlik kurallarını uygular. Bu nedenle, msvcm90.dll yerel kod içerdiğinden ve kod erişimi güvenlik ilkesi üzerinde zorlanamadığından, bu bağımlılığı kaldırmak gerekir.

Uygulamanız C çalışma zamanı kitaplığı 'nın herhangi bir işlevselliğini kullanmıyorsa ve bu kitaplıktaki bağımlılığı kodunuzda kaldırmak istiyorsanız, **/nodefaultlib: msvcmrt. lib** bağlayıcı seçeneğini kullanmanız ve ptrustm. lib ya da ptrustmd. lib ile bağlantı oluşturmanız gerekir. Bu kitaplıklar, bir uygulamanın başlatılması ve başlatılmasına yönelik nesne dosyalarını, başlatma kodu tarafından kullanılan özel durum sınıflarını ve yönetilen özel durum işleme kodunu içerir. Bu kitaplıklarınızdan birinde bağlama, msvcm90.dll bağımlılığı kaldırır.

> [!NOTE]
> Derleme geri başlatmasının sırası, ptrust kitaplıklarını kullanan uygulamalar için farklılık gösterebilir. Normal uygulamalar için derlemeler genellikle yüklendikleri sırada kaldırılır, ancak bu garanti edilmez. Kısmi güven uygulamaları için, derlemeler genellikle yüklendikleri sırayla kaldırılır. Bu da garanti edilmez.

### <a name="to-create-a-partially-trusted-mixed-clr-application"></a>Kısmen güvenilen bir karma (/CLR) uygulaması oluşturmak için

1. msvcm90.dll bağımlılığı kaldırmak için, **/nodefaultlib: msvcmrt. lib** bağlayıcı seçeneğini kullanarak bu kitaplığı dahil etmek için bağlayıcı olarak belirtmeniz gerekir. Visual Studio geliştirme ortamı veya program aracılığıyla bunun nasıl yapılacağı hakkında bilgi için bkz. [/nodefaultlib (kitaplıkları Yoksay)](../build/reference/nodefaultlib-ignore-libraries.md).

1. Ptrustm kitaplıklarından birini bağlayıcı girişi bağımlılıklarına ekleyin. Uygulamanızı yayın modunda oluşturuyorsanız ptrustm. lib kullanın. Hata ayıklama modu için ptrustmd. lib kullanın. Visual Studio geliştirme ortamı veya program aracılığıyla bunun nasıl yapılacağı hakkında bilgi için bkz [.. Bağlayıcı girişi olarak lib dosyaları](../build/reference/dot-lib-files-as-linker-input.md).

## <a name="see-also"></a>Ayrıca bkz.

[Karışık (yerel ve yönetilen) derlemeler](../dotnet/mixed-native-and-managed-assemblies.md)<br/>
[Karışık derlemeleri başlatma](../dotnet/initialization-of-mixed-assemblies.md)<br/>
[Karışık derlemeler için kitaplık desteği](../dotnet/library-support-for-mixed-assemblies.md)<br/>
[/Link (Seçenekleri Bağlayıcıya Geçir)](../build/reference/link-pass-options-to-linker.md)
