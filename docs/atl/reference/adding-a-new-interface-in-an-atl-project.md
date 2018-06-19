---
title: ATL projesinde yeni bir arabirim ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.appwiz.ATL.interface
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding to ATL objects
- Implement Interface ATL wizard
- controls [ATL], interfaces
- ATL projects, adding interfaces
ms.assetid: 7d34b023-2c6b-4155-aca3-d47a40968063
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2c9d0ef4c14760d596a4aa26fa2a929da26c67b
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356751"
---
# <a name="adding-a-new-interface-in-an-atl-project"></a>ATL projesinde yeni bir arabirim ekleme
Nesne veya denetim için bir arabirim eklediğinizde, bu arabiriminde her yöntemi için tamamlanmamış işlevleri oluşturun. Nesne veya denetim içinde yalnızca şu anda var olan bir tür kitaplığı'nda bulunan arabirimleri ekleyebilirsiniz. Ayrıca, sınıf arabirimi Ekle uygulamalıdır [BEGIN_COM_MAP](com-map-macros.md#begin_com_map) makrosu veya proje bağlanıyorsa olmalıdır `coclass` özniteliği.  
  
 Yeni bir arabirimi denetiminizi iki yoldan biriyle ekleyebilirsiniz: el ile veya sınıf görünümündeki kod sihirbazları kullanarak.  
  
### <a name="to-use-code-wizards-in-class-view-to-add-an-interface-to-an-existing-object-or-control"></a>Kod sihirbazları Sınıf Görünümü'nde bir varolan nesne veya denetim bir arabirim eklemek için kullanılacak  
  
1.  İçinde [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), bir denetimin sınıf adını sağ tıklatın. Örneğin, tam denetim veya bileşik denetim veya kendi üstbilgi dosyasında BEGIN_COM_MAP makrosu uygulayan herhangi bir denetim sınıf.  
  
2.  Kısayol menüsünde **Ekle**ve ardından **arabirimi uygulama**.  
  
3.  Uygulama arabirimleri seçin [arabirim Uygulama Sihirbazı'nı](../../ide/implement-interface-wizard.md). Arabirimi içinde kullanılabilir tüm typelib mevcut değilse daha sonra onu el ile .idl dosyasına eklemeniz gerekir.  
  
### <a name="to-add-a-new-interface-manually"></a>Yeni bir arabirimi el ile eklemek için  
  
1.  Yeni arabirimi tanımını .idl dosyasına ekleyin.  
  
2.  Nesne veya arabirim denetiminden türetilir.  
  
3.  Yeni bir [COM_INTERFACE_ENTRY](com-interface-entry-macros.md#com_interface_entry) arabirimi veya proje bağlanıyorsa ekleme `coclass` özniteliği.  
  
4.  Arabirimde yöntemleri uygulayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [ATL Proje Sihirbazı](../../atl/reference/atl-project-wizard.md)   
 [Visual C++ proje türleri](../../ide/visual-cpp-project-types.md)   
 [Uygulama sihirbazları kullanarak masaüstü projeleri oluşturma](../../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [ATL ve C çalışma zamanı koduyla programlama](../../atl/programming-with-atl-and-c-run-time-code.md)   
 [ATL COM nesneleri temelleri](../../atl/fundamentals-of-atl-com-objects.md)   
 [Varsayılan ATL Projesi Yapılandırmaları](../../atl/reference/default-atl-project-configurations.md)

