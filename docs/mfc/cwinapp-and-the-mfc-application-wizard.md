---
description: 'Ayrıntılar hakkında daha fazla bilgi edinin: CWinApp ve MFC Uygulama Sihirbazı'
title: CWinApp ve MFC Uygulama Sihirbazı
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: 1ce1f0a84aa5a0f123f9fa8654d1ce286c47d1d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309270"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp ve MFC Uygulama Sihirbazı

Bir iskelet uygulaması oluşturduğunda, MFC Uygulama Sihirbazı [CWinApp](reference/cwinapp-class.md)'dan türetilmiş bir uygulama sınıfı bildirir. MFC Uygulama Sihirbazı aşağıdaki öğeleri içeren bir uygulama dosyası da oluşturur:

- Uygulama sınıfı için bir ileti eşlemi.

- Boş bir sınıf Oluşturucusu.

- Sınıfın tek ve tek bir nesnesini bildiren bir değişken.

- `InitInstance`Üye işlevinizin standart bir uygulamasıdır.

Uygulama sınıfı, proje başlığına ve ana kaynak dosyalarına yerleştirilir. Oluşturulan sınıf ve dosyaların adları, MFC Uygulama Sihirbazı 'nda sağladığınız proje adına göre yapılır. Bu sınıfların kodunu görüntülemenin en kolay yolu [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code)kullanmaktır.

Sağlanan standart uygulamalar ve ileti haritası birçok amaçla yeterlidir, ancak bunları gerektiği gibi değiştirebilirsiniz. Bu uygulamaların en ilginç öğesi `InitInstance` üye işlevdir. Genellikle, ' nin iskelet uygulamasına kod ekleyeceksiniz `InitInstance` .

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: uygulama sınıfı](cwinapp-the-application-class.md)<br/>
[Geçersiz kılınabilir CWinApp Üye Işlevleri](overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](special-cwinapp-services.md)
