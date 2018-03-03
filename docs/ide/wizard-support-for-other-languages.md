---
title: "Diğer diller için sihirbaz desteği | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8ef95c252621aa7f725098dfcd08c7b5b3620826
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="wizard-support-for-other-languages"></a>Diğer Diller için Sihirbaz Desteği
Visual Studio yüklediğinizde, kurulum uygulaması sisteminizde listelenen yerel algılar ve uygun dil şablon ya da yerel şablonlarını yükler. Örneğin, Batı Avrupa yerel ayarlar için İngilizce, Fransızca, İtalyanca, İspanyolca ve Almanca Kurulum yükler. Bu diller görünür **kaynak dili** listesini [uygulama türü](../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.  
  
## <a name="language-templates"></a>Dil şablonları  
 Şablonları ANSI kodlamasını dayalı ve tüm kaynakları tüm sistemlerde düzenlenebilir olduğundan tüm şablonları tüm sistemlere yüklenir. Örneğin, varsayılan olarak, Fransızca sistem Japonca kaynaklardaki düzenleyemezsiniz.  
  
 Windows 2000 veya üstünü kullanıyorsanız ve başka bir dilde MFC uygulaması oluşturmak istiyorsanız, sisteminize Visual Studio Installer ortam (Disk 1) uygun dili için şablon dizinine kopyalamalısınız.  
  
> [!NOTE]
>  Oluşturulan proje düzenlemek için seçilen dile ilişkin uygun yerel sistemi yerel ayarınız ayarlamanız gerekir.  
  
 Her bir klasör \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\ dizinde atanmış aşağıdaki tabloda listelendiği gibi şablonlarıdır. İstenen dil şablonu erişmek için bilgisayarınızdaki \mfcappwiz\templates\ dizinine uygun klasöre kopyalayın. Klasör kopyalandıktan sonra dil görünür **kaynak dili** listesini **uygulama türü** MFC Uygulama Sihirbazı sayfası.  
  
### <a name="language-templates-provided-in-visual-studio-net"></a>Visual Studio .NET sağlanan dil şablonları  
  
|Dil|Şablon|  
|--------------|--------------|  
|seçenekleri yerine|1028|  
|ve|2052|  
|İngilizce|1033|  
|Fransızca|1036|  
|Almanca|1031|  
|İtalyanca|1040|  
|Japonca|1041|  
|Kore Dili|1042|  
|İspanyolca|3082|  
  
## <a name="format-of-visual-c-wizard-generated-files"></a>Visual C++ sihirbaz tarafından oluşturulan dosya biçimi  
 Visual Studio yüklü dil sürümünü sistem yerel ayarı eşleşmediğinde Visual C++ sihirbazları Unicode projeleri oluşturur. Örneğin, Visual Studio'nun Japonca sürümü bölgesel ayarları Japonca dışındaki herhangi bir dil için ayarlanmış olan bir bilgisayara yüklendiğinde, Visual C++ sihirbazları Unicode dosyaları oluşan projeleri oluşturur. Bu, Windows çok dilli (MUI) paketleri ile ayarlanan makinelerde yaygındır.  
  
 Bu davranış, sistem yerel ayarı Visual Studio dil sürümü ile aynı olacak şekilde, ayarlanan sistemlerinden farklıdır. Bu durumda, proje dosyalarını, sistem kod sayfası ANSI oluşturulur.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Visual C++ projeleri için oluşturulan dosya türleri](../ide/file-types-created-for-visual-cpp-projects.md)   
 [Visual C++ proje oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)