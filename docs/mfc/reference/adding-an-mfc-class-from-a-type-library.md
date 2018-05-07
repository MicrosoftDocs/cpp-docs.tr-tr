---
title: Tür kitaplığından MFC sınıfı ekleme | Microsoft Docs
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
ms.openlocfilehash: 349d06d7fecb82af64fbf2d3b2ebe54689b3b292
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Tür Kitaplığından Bir MFC Sınıfı Ekleme
Bir MFC sınıfı kullanılabilir Tür Kitaplığı'nda bir arabirim oluşturmak için bu sihirbazı kullanın. Bir MFC sınıfı ekleme bir [MFC uygulaması](../../mfc/reference/creating-an-mfc-application.md), bir [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md), veya bir [MFC ActiveX denetimini](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  MFC projenize bir tür kitaplığından bir sınıf eklemek için etkin Otomasyon oluşturmak gerekmez.  
  
 Tür kitaplığı ikili yöntemleri, parametreler ve dönüş türleri ile birlikte tanımlayan bir bileşen tarafından sergilenen arabirimlerle açıklamasını içerir. Tür kitaplığı görünmesini kayıtlı olması gerekir **kullanılabilir tür kitaplıklarının** Typelib sihirbazından Sınıf Ekle listesinde. "İçinde dağıtılmış COM: tür kitaplıklarını ve dil tümleştirme" daha fazla bilgi için MSDN Kitaplığı'nda bkz.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>Tür kitaplığından bir MFC sınıfı ekleme  
  
1.  Her ikisinde **Çözüm Gezgini** veya [sınıf görünümü](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), sınıf eklemek istediğiniz proje adına sağ tıklayın.  
  
2.  Kısayol menüsünden tıklatın **Ekle**ve ardından **sınıfı Ekle**.  
  
3.  İçinde [sınıfı Ekle](../../ide/add-class-dialog-box.md) Şablonlar bölmesinde iletişim kutusu **Typelib MFC sınıfı**ve ardından **açık** görüntülenecek [Typelib sihirbazından sınıf ekleme ](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 Sihirbazı'nda bir tür kitaplığı birden fazla sınıfında ekleyebilirsiniz. Benzer şekilde, tek bir sihirbaz oturumunda birden fazla tür kitaplığından sınıfları ekleyebilirsiniz.  
  
 Türetilen bir MFC Sınıf Sihirbazı'nı oluşturur [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), seçilen tür kitaplığından eklediğiniz her bir arabirim için. `COleDispatchDriver` OLE Otomasyon istemci tarafı uygular.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Otomasyon istemcileri](../../mfc/automation-clients.md)   
 [Otomasyon İstemcileri: Tür Kitaplıklarını Kullanma](../../mfc/automation-clients-using-type-libraries.md)

