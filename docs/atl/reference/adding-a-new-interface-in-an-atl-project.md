---
title: ATL Projesine Yeni Arabirim Ekleme
ms.date: 11/04/2016
f1_keywords:
- vc.appwiz.ATL.interface
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
ms.openlocfilehash: 8bf0138f85929e06b67e9a2e294eda8a2f385e1a
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499389"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL Projesine Yeni Arabirim Ekleme

Nesneniz veya denetiinize bir arabirim eklediğinizde, bu arabirimdeki her bir yöntem için saplaması-Out işlevleri oluşturursunuz. Nesneniz veya denetiminiz içinde, şu anda var olan bir tür kitaplığında bulunan arabirimleri ekleyebilirsiniz. Ayrıca, arabirimi eklediğiniz sınıfın [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) makrosunu uygulaması gerekir, aksi takdirde proje özniteliğine sahip olması gerekir `coclass` .

Yeni bir arabirimi, denetiyinize iki şekilde ekleyebilirsiniz: el ile veya Sınıf Görünümü kod sihirbazları kullanma.

## <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Varolan bir nesneye veya denetime arabirim eklemek için Sınıf Görünümü kod sihirbazları kullanmak için

1. [Sınıf görünümü](/visualstudio/ide/viewing-the-structure-of-code), bir denetimin sınıf adına sağ tıklayın. Örneğin, tam denetim veya bileşik denetim ya da onun başlık dosyasında bir BEGIN_COM_MAP makrosunu uygulayan herhangi bir denetim sınıfı.

1. Kısayol menüsünde, **Ekle**' ye ve ardından **arabirimi Uygula**' ya tıklayın.

1. [Arabirim uygulama Sihirbazı](../../ide/implementing-an-interface-visual-cpp.md#implement-interface-wizard)'nda uygulanacak arabirimleri seçin. Arabirim kullanılabilir herhangi bir TypeLib 'de yoksa, bunu. IDL dosyasına el ile eklemeniz gerekir.

## <a name="to-add-a-new-interface-manually"></a>Yeni bir arabirimi el ile eklemek için

1. Yeni arabiriminiz tanımını. IDL dosyasına ekleyin.

1. Nesne veya denetim arabiriminden türetebilirsiniz.

1. Arabirim için yeni bir [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) oluşturun veya proje ilişkilendirilebildiği takdirde `coclass` özniteliği ekleyin.

1. Yöntemi arayüzde uygulayın.

## <a name="see-also"></a>Ayrıca bkz.

[ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)<br/>
[Visual Studio 'da C++ proje türleri](../../build/reference/visual-cpp-project-types.md)<br/>
[ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)<br/>
[ATL COM nesnelerinin temelleri](../../atl/fundamentals-of-atl-com-objects.md)<br/>
[Varsayılan ATL Proje yapılandırması](../../atl/reference/default-atl-project-configurations.md)
