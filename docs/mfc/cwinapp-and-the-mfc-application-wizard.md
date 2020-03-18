---
title: CWinApp ve MFC Uygulama Sihirbazı
ms.date: 11/04/2016
helpviewer_keywords:
- application wizards [MFC], and CWinApp
- CWinApp class [MFC], and MFC Application Wizard
- MFC, wizards
ms.assetid: f8ac0491-3302-4e46-981d-0790624eb8a2
ms.openlocfilehash: 1a46842d7b4d6a588da585d63e2ad56982bb0ff8
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79447033"
---
# <a name="cwinapp-and-the-mfc-application-wizard"></a>CWinApp ve MFC Uygulama Sihirbazı

Bir iskelet uygulaması oluşturduğunda, MFC Uygulama Sihirbazı [CWinApp](../mfc/reference/cwinapp-class.md)'dan türetilmiş bir uygulama sınıfı bildirir. MFC Uygulama Sihirbazı aşağıdaki öğeleri içeren bir uygulama dosyası da oluşturur:

- Uygulama sınıfı için bir ileti eşlemi.

- Boş bir sınıf Oluşturucusu.

- Sınıfın tek ve tek bir nesnesini bildiren bir değişken.

- `InitInstance` üye işlevinizin standart bir uygulamasıdır.

Uygulama sınıfı, proje başlığına ve ana kaynak dosyalarına yerleştirilir. Oluşturulan sınıf ve dosyaların adları, MFC Uygulama Sihirbazı 'nda sağladığınız proje adına göre yapılır. Bu sınıfların kodunu görüntülemenin en kolay yolu [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code)kullanmaktır.

Sağlanan standart uygulamalar ve ileti haritası birçok amaçla yeterlidir, ancak bunları gerektiği gibi değiştirebilirsiniz. Bu uygulamaların en ilginç öğesi `InitInstance` member işlevidir. Genellikle, `InitInstance`iskelet uygulamasına kod ekleyeceksiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)<br/>
[Geçersiz Kılınabilir CWinApp Üye İşlevleri](../mfc/overridable-cwinapp-member-functions.md)<br/>
[Özel CWinApp Hizmetleri](../mfc/special-cwinapp-services.md)
