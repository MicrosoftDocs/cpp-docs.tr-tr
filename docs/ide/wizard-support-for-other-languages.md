---
title: Diğer diller için sihirbaz desteği | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.appwiz.EastAsianLanguages
dev_langs:
- C++
helpviewer_keywords:
- wizards [C++], language support
- language support for MFC projects
- projects [C++], language support
ms.assetid: b653c673-0687-455c-885f-15d7e2f4149d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c33858e02fd8bad03e03a963e940f215d528157d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46395147"
---
# <a name="wizard-support-for-other-languages"></a>Diğer Diller için Sihirbaz Desteği

Visual Studio yüklediğinizde, kurulum uygulaması sisteminizdeki listelenen yerel algılar ve uygun dil şablonu veya yerel şablonlarını yükler. Örneğin, Batı Avrupa yerel ayara yönelik Kurulum, İngilizce, Fransızca, İtalyanca, İspanyolca ve Almanca yükler. Bu diller görünür **kaynak dili** listesini [uygulama türü](../mfc/reference/application-type-mfc-application-wizard.md) MFC Uygulama Sihirbazı sayfası.

## <a name="language-templates"></a>Dil şablonları

Şablonları ANSI kodlaması tabanlı ve tüm kaynaklar tüm sistemlerde düzenlenebilir olmadığından, tüm şablonları tüm sistemlerde yüklenir. Örneğin, varsayılan olarak, Fransızca sistem Japonca kaynaklardaki düzenleyemezsiniz.

Windows 2000 veya üstünü kullandığınız ve başka bir dilde bir MFC uygulaması oluşturmak istiyorsanız, sisteminize (Disk 1) Visual Studio yükleyicisi medyadan uygun dili için şablon dizini kopyalamalısınız.

> [!NOTE]
>  Oluşturulan proje düzenlemek için seçilen dile uygun yerel sistemi yerel ayarınız ayarlamanız gerekir.

Her bir klasör \Microsoft Visual Studio .NET 2003\Vc7\VCWizards\mfcappwiz\templates\ dizinde atanan aşağıdaki tabloda listelendiği gibi şablonlardır. İstenen dil şablonu erişmek için ilgili klasörü bilgisayarınızda \mfcappwiz\templates\ dizinine kopyalayın. Klasör kopyaladıktan sonra dil olarak görünür **kaynak dili** listesini **uygulama türü** MFC Uygulama Sihirbazı sayfası.

### <a name="language-templates-provided-in-visual-studio-net"></a>Visual Studio. NET'te sağlanan dil şablonları

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

Visual Studio'nun yüklü dil sürümü sistem yerel ayarı eşleşmediğinde Visual C++ sihirbazları Unicode projeleri oluşturur. Örneğin, Japonca sürümü Visual Studio'nun bölgesel ayarları Japonca dışındaki herhangi bir dil için ayarlanmış olan bir bilgisayara yüklendiğinde, Visual C++ sihirbazları Unicode dosya oluşan projeleri oluşturur. Bu, Windows çok dilli (MUI) paketleri ile ayarlanan makinelerde yaygındır.

Bu davranış, sistem yerel Visual Studio dil sürümü ile aynıdır, ayarlanan sistemlerinden farklıdır. Bu durumda, proje dosyaları, sistem kod sayfası ANSI oluşturulur.

## <a name="see-also"></a>Ayrıca Bkz.

[Visual C++ Projeleri için Oluşturulan Dosya Türleri](../ide/file-types-created-for-visual-cpp-projects.md)<br>
[Visual C++ proje oluşturma ve yönetme](../ide/creating-and-managing-visual-cpp-projects.md)