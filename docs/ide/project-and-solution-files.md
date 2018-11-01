---
title: Proje ve Çözüm Dosyaları
ms.date: 11/04/2016
f1_keywords:
- vc.files.projectandsolution
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
ms.openlocfilehash: 8b84c28db2afb914a73a0cb4d0d778c99cfd6635
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616643"
---
# <a name="project-and-solution-files"></a>Proje ve Çözüm Dosyaları

Visual Studio'da bir proje oluşturduğunuzda aşağıdaki dosyalar oluşturulur. Bunlar, çözümdeki proje dosyalarını yönetmek için kullanılır.

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|--------------|------------------------|--------------------------------|-----------------|
|*Solname*.sln|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Çözüm* dosya. Bir projenin tüm öğeleri veya birden çok proje tek bir çözüm düzenler.|
|*PROJNAME*.suo|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Çözüm seçenekleri* dosya. Çözümde bir proje veya dosya açın her zaman, istediğiniz davranışı ve görünümü, sahip olacak şekilde özelleştirmelerinizi çözümü depolar.|
|*PROJNAME*.vcxproj|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Proje* dosya. Bu, her projeye özel bilgileri depolar. (Önceki sürümlerde, bu dosya olarak adlandırılıyordu *Projname*.vcproj veya *Projname*.dsp.) Visual C++ proje dosyası örneği için bkz: [proje dosyaları](../ide/project-files.md).|
|*PROJNAME*.vcxitems|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Paylaşılan öğeler projesi* dosya. Bu proje oluşturulan değil.  Bunun yerine, proje başka bir C++ projesi tarafından başvurulabilir ve dosyalarından başvurulan projenin yapı işleminin bir parçası olur. Bu platformlar arası C++ projeleriyle ortak kod paylaşmak için kullanılabilir.|
|*PROJNAME*.sdf|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Gözatma veritabanı* dosya. Göz atma ve gezinti özellikleri gibi destekleyen **Goto tanımı**, **tüm başvuruları Bul**, ve **sınıf görünümü**. Üst bilgi dosyaları ayrıştırma tarafından oluşturulur.|
|*PROJNAME.* vcxproj.filters|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Filtreleri* dosya. Bu, çözüme bir dosyasının nereye yerleştirileceğini belirtir. Örneğin, bir .h dosyası yerleştirin **üst bilgi dosyaları** düğümü.|
|*PROJNAME.* vcxproj.user|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez.|*Geçiş kullanıcı* dosya. Bir projeyi Visual Studio 2008'den geçirildikten sonra bu dosya tüm .vsprops dosyasından dönüştürülen bilgileri içerir.|
|*PROJNAME*.idl|*PROJNAME*|Kaynak|(Projeye özgü) Bir denetimi tür kitaplığına arabirimi tanım dili (IDL) kaynak kodunu içerir. Bu dosya, bir tür kitaplığı oluşturmak için Visual C++ tarafından kullanılır. Oluşturulan kitaplığı diğer Otomasyon istemcileri için Denetim arabirimini kullanıma sunar. Daha fazla bilgi için [arabirim tanımı (IDL) dosya](/windows/desktop/Rpc/the-interface-definition-language-idl-file) Windows SDK.|
|Readme.txt|*PROJNAME*|Proje|*Beni oku* dosya. Uygulama Sihirbazı tarafından oluşturulan ve bir proje dosyalarında açıklanır.|

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)