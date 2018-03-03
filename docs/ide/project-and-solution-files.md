---
title: "Proje ve çözüm dosyaları | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.files.projectandsolution
dev_langs:
- C++
helpviewer_keywords:
- project files [C++]
- file types [C++], makefiles
- .sdf, browsing database file
- Makefile projects
- browsing database file, .sdf
- file types [C++], project files
ms.assetid: 5823b954-36cf-42d3-8fd5-25bab3ef63d9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 03797d266dc0f3104d6153b9d946d06ac963fafc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="project-and-solution-files"></a>Proje ve Çözüm Dosyaları
Visual Studio'da bir proje oluşturduğunuzda aşağıdaki dosyalar oluşturulur. Bunlar, çözümdeki proje dosyalarını yönetmek için kullanılır.  
  
|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|  
|--------------|------------------------|--------------------------------|-----------------|  
|*Solname*.sln|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Çözüm* dosya. Tüm öğeleri bir projenin veya birden çok proje tek bir çözümde düzenler.|  
|*PROJNAME*.suo|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Çözüm seçenekleri* dosya. Çözümdeki bir proje veya dosyayı açmak her zaman, istediğiniz davranışı ve görünümü, sahip olması özelleştirmelerinizi çözüm için depolar.|  
|*PROJNAME*.vcxproj|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Proje* dosya. Her proje için özel bilgileri depolar. (Önceki sürümlerde, bu dosya adlı *Projname*.vcproj veya *Projname*.dsp.) Visual C++ proje dosyası örneği için bkz: [proje dosyalarını](../ide/project-files.md).|  
|*PROJNAME*.vcxitems|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Paylaşılan öğeler proje* dosya. Bu proje yerleşik değil.  Bunun yerine, projenin başka bir C++ projesi tarafından başvurulabilir ve dosyalarından başvuru projenin derleme işleminin bir parçası olur. Bu ortak kodun platformlar arası C++ projeleri ile paylaşmak için kullanılabilir.|
|*PROJNAME*.sdf|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Veritabanına gözatma* dosya. Gözatma ve gezinti özellikleri gibi destekleyen **Goto tanımı**, **tüm başvuruları Bul**, ve **sınıf görünümü**. Üstbilgi dosyaları ayrıştırma tarafından oluşturulur.|  
|*PROJNAME.* vcxproj.filters|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Filtreleri* dosya. Çözüme eklendi dosyasının nereye yerleştirileceğini belirler. Örneğin, bir .h dosyası put **üstbilgi dosyaları** düğümü.|  
|*PROJNAME.* vcxproj.user|*PROJNAME*|Çözüm Gezgini'nde görüntülenmez|*Geçiş kullanıcı* dosya. Visual Studio 2008'den bir proje geçirildikten sonra bu dosyayı herhangi bir .vsprops dosyadan dönüştürüldü bilgiler içerir.|  
|*PROJNAME*.idl|*PROJNAME*|Kaynak|(Proje özgü) Bir denetim tür kitaplığı arabirimi Açıklama Dili (IDL) kaynak kodunu içerir. Bu dosya, bir tür kitaplığı oluşturmak için Visual C++ tarafından kullanılır. Oluşturulan kitaplığı diğer Otomasyon istemcileri için Denetim arabirimi sunar. Daha fazla bilgi için bkz: [arabirim tanımı (IDL) dosya](http://msdn.microsoft.com/library/windows/desktop/aa378712) Windows SDK.|  
|Readme.txt|*PROJNAME*|Proje|*Beni oku* dosya. Uygulama Sihirbazı tarafından oluşturulan ve bir proje dosyalarında açıklanır.|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)