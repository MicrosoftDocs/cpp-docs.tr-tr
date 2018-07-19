---
title: Tür kitaplığından bir MFC sınıfı ekleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 662754ae4f0f95160f18682f35eb2f7951e7e344
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/13/2018
ms.locfileid: "39026558"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Tür Kitaplığından Bir MFC Sınıfı Ekleme
Kullanılabilen tür kitaplığında bir arabirimden bir MFC sınıfı oluşturmak için bu sihirbazı kullanın. Bir MFC sınıfı için ekleyebileceğiniz bir [MFC uygulaması](../../mfc/reference/creating-an-mfc-application.md), bir [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md), veya bir [MFC ActiveX denetimi](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Tür kitaplığından bir sınıf eklemek için etkin Otomasyonu ile MFC projenizi oluşturmak gerekmez.  
  
 Bir tür kitaplığı ikili yöntemlerin parametreleri ve dönüş türleri birlikte tanımlama, bir bileşen tarafından kullanıma sunulan arabirimler açıklamasını içerir. Tür kitaplığı içinde görünmesi için kaydedilmelidir **kullanılabilir tür kitaplıklarını** Typelib sihirbazından Sınıf Ekle listesinde. "İçinde dağıtılmış COM: tür kitaplıklarını ve dil tümleştirme" daha fazla bilgi için MSDN Kitaplığı'nda bkz.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>Tür kitaplığından bir MFC sınıfı ekleme  
  
1.  Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925), sınıfa eklemek istediğiniz proje adına sağ tıklayın.  
  
2.  Kısayol menüsünden tıklayın **Ekle**ve ardından **sınıfı Ekle**.  
  
3.  İçinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) Şablonlar bölmesinde, iletişim kutusu **typelib'den MFC sınıfı**ve ardından **açık** görüntülenecek [Typelib sihirbazından sınıf ekleme ](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 Sihirbazda bir tür kitaplığında birden fazla sınıf ekleyebilirsiniz. Benzer şekilde, tek bir sihirbaz oturumunda birden fazla tür kitaplığından sınıfları ekleyebilirsiniz.  
  
 MFC sınıfından türetilen bir sihirbaz [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), seçilen tür kitaplığından eklediğiniz her arabirim için. `COleDispatchDriver` OLE Otomasyonu nesnesi etkin tarafını uygular.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon istemcileri](../../mfc/automation-clients.md)   
 [Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../../mfc/automation-clients-using-type-libraries.md)

