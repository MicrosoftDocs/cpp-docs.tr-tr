---
description: 'Daha fazla bilgi edinin: proje ve çözüm dosyaları'
title: Proje ve Çözüm Dosyaları
ms.date: 05/06/2019
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
ms.openlocfilehash: e91876f1c405b8a145e0a2d94195a424101b469b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225784"
---
# <a name="project-and-solution-files"></a>Proje ve Çözüm Dosyaları

Visual Studio 'da bir proje oluşturduğunuzda aşağıdaki dosyalar oluşturulur. Çözümdeki proje dosyalarını yönetmek için kullanılırlar.

|Kısaltın|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|--------------|------------------------|--------------------------------|-----------------|
|*Soladı*. sln|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Çözüm* dosyası. Bir projenin veya birden çok projenin tüm öğelerini tek bir çözümde düzenler.|
|*ProjName*. suo|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Çözüm seçenekleri* dosyası. Çözümdeki bir proje veya dosyayı her açışınızda istediğiniz görünümü ve davranışı içeren çözüm için özelleştirmelerinizi depolar.|
|*ProjName*. vcxproj|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Proje* dosyası. Her bir projeye özel bilgileri depolar. (Önceki sürümlerde bu dosya *ProjName*. vcproj veya *ProjName*. DSP olarak adlandırılmıştı.) C++ proje dosyası (. vcxproj) örneği için bkz. [proje dosyaları](project-files.md).|
|*ProjName*. vcxıtems|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Paylaşılan öğeler proje* dosyası. Bu proje derlenmedi.  Bunun yerine, projeye başka bir C++ projesi tarafından başvurulabilir ve bu proje, başvuran projenin derleme sürecinin bir parçası haline gelir. Bu, platformlar arası C++ projeleriyle ortak kod paylaşmak için kullanılabilir.|
|*ProjName*. sdf|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Göz atma veritabanı* dosyası. **Goto**, **tüm başvuruları bul** ve **sınıf görünümü** göz atma ve gezinme özelliklerini destekler. Üst bilgi dosyaları ayrıştırılmasından oluşturulur.|
|*ProjName*. vcxproj. Filters|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Filtreler* dosyası. Çözüme eklenen bir dosyanın nereye yerleştirileceğini belirtir. Örneğin, bir. h dosyası **başlık dosyaları** düğümüne konur.|
|*ProjName*. vcxproj. User|*ProjName*|Çözüm Gezgini görüntülenmiyor|*Geçiş Kullanıcı* dosyası. Visual Studio 2008 ' den bir proje geçirildikten sonra, bu dosya herhangi bir. vsprops dosyasından dönüştürülen bilgiler içerir.|
|*ProjName*. IDL|*ProjName*|Kaynak|(Projeye özel) Bir denetim türü kitaplığı için arabirim Açıklama Dili (IDL) kaynak kodunu içerir. Bu dosya Visual C++ tarafından bir tür kitaplığı oluşturmak için kullanılır. Oluşturulan kitaplık, diğer otomasyon istemcilerine denetimin arabirimini kullanıma sunar. Daha fazla bilgi için Windows SDK [arabirim tanımı (IDL) dosyasına](/windows/win32/Rpc/the-interface-definition-language-idl-file) bakın.|
|Readme.txt|*ProjName*|Project|*Beni oku* dosyası. Uygulama Sihirbazı tarafından oluşturulur ve bir projedeki dosyaları tanımlar.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)
