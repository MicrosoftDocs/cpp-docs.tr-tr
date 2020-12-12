---
description: 'Hakkında daha fazla bilgi edinin: yardım dosyaları (HTML Yardımı)'
title: Yardım Dosyaları (HTML Yardım)
ms.date: 11/04/2016
helpviewer_keywords:
- file types [C++], HTML Help files
ms.assetid: d30a1b1b-318f-4a78-8b60-93da53a224a8
ms.openlocfilehash: 0a2b92300683fcc4f0ced365a6750f6e73da10f8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191608"
---
# <a name="help-files-html-help"></a>Yardım Dosyaları (HTML Yardım)

Aşağıdaki dosyalar, **içeriğe duyarlı yardım** onay kutusunu seçerek ve ardından MFC Uygulama sihirbazının [Gelişmiş Özellikler](../../mfc/reference/advanced-features-mfc-application-wizard.md) sayfasında **HTML yardım biçimi** ' ni seçerek uygulamanıza yardım desteğini HTML Yardım türünü eklediğinizde oluşturulur.

|Dosya adı|Dizin konumu|Çözüm Gezgini konumu|Açıklama|
|---------------|------------------------|--------------------------------|-----------------|
|*ProjName*. hhp|*ProjName*\hlp|HTML Yardım dosyaları|Yardım Projesi dosyası. Yardım dosyalarını bir. HXS dosyasında veya. chm dosyasında derlemek için gereken verileri içerir.|
|*ProjName*. HHK|*ProjName*\hlp|HTML Yardım dosyaları|Yardım konularının bir dizinini içerir.|
|*ProjName*. hhc|*ProjName*\hlp|HTML Yardım dosyaları|Yardım projesinin içeriği.|
|Makehtmlhelp.bat|*ProjName*|Kaynak dosyalar|Proje derlendiğinde yardım projesi oluşturmak için sistem tarafından kullanılır.|
|Afxcore.htm|*ProjName*\hlp|HTML Yardım konuları|Standart MFC komutları ve ekran nesneleri için standart Yardım konularını içerir. Bu dosyaya kendi Yardım konularınızı ekleyin.|
|Afxprint.htm|*ProjName*\hlp|HTML Yardım konuları|Yazdırma komutları için yardım konularını içerir.|
|*. jpg; \*. gif|*ProjName*\Hlp\ımages|Kaynak Dosyalar|Oluşturulmuş farklı yardım dosyası konuları için görüntü içerir.|

## <a name="see-also"></a>Ayrıca bkz.

[Visual Studio C++ projeleri için oluşturulan dosya türleri](file-types-created-for-visual-cpp-projects.md)
