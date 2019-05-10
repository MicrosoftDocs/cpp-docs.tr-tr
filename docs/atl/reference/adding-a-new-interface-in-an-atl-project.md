---
title: ATL projesine yeni arabirim ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 15283439bdcf76fea64d677ad84bee333833dc71
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2019
ms.locfileid: "65221229"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL projesine yeni arabirim ekleme

Bir arabirim, nesne veya denetim eklediğinizde, o arabirimi her yöntemi için tamamlanmamış işlevleri oluşturun. Nesne veya denetim yalnızca şu anda var olan bir tür kitaplığında bulunan arabirimleri ekleyebilirsiniz. Ayrıca, sınıf, arabirim Ekle uygulamalıdır [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) makrosu veya proje bağlanıyorsa olmalıdır `coclass` özniteliği.

Yeni bir arabirim iki yoldan biriyle denetiminizi ekleyebilirsiniz: el ile veya Sınıf Görünümü'nde kod sihirbazları kullanarak.

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Kod sihirbazları, var olan nesne veya denetim için bir arabirim eklemek için Sınıf Görünümü'nde kullanmak için

1. İçinde [sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), denetim sınıf adına sağ tıklayın. Örneğin, bir tam denetim veya bileşik denetim veya BEGIN_COM_MAP makrosu, üst bilgi dosyası içinde uygulayan herhangi bir denetim sınıf.

1. Kısayol menüsünde **Ekle**ve ardından **arabirim uygulama**.

1. İçinde uygulanacak arabirimleri seçin [arabirim Uygulama Sihirbazı'nı](../../ide/implement-interface-wizard.md). Arabirimi kullanılabilir tüm TypeLib'de mevcut değilse, ardından onu elle .idl dosyasına eklemeniz gerekir.

## <a name="to-add-a-new-interface-manually"></a>Yeni bir arabirim el ile eklemek için

1. Yeni, arabirim tanımı .idl dosyasına ekleyin.

1. Nesne veya arabirimi denetiminden birisinden türetin.

1. Yeni bir [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) arabirimin veya proje bağlanıyorsa ekleme `coclass` özniteliği.

1. Arabirimdeki yöntemleri uygulayın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Projesi Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[C++Visual Studio Proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL ve C Çalışma Zamanı Koduyla Programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM Nesnelerinin Temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)
