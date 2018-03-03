---
title: "OLE arka planı: MFC uygulaması | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IMarshall
- IMoniker
dev_langs:
- C++
helpviewer_keywords:
- MFC libraries, implementing
- OLE MFC library implementation
- OLE IMarshal interface
- IMoniker interface, MFC
- IMarshall class [MFC]
- OLE, compound files
- OLE IMoniker interface
- OLE IUnknown
ms.assetid: 2b67016a-d78e-4d60-925f-c28ec8fb6180
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 530cc14135fd38e2177e00dc87974e96ffe24b6c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="ole-background-mfc-implementation"></a>OLE Arka Planı: MFC Uygulaması
Boyutu ve karmaşıklığı ham OLE API nedeniyle, doğrudan OLE uygulamaları yazmak için çağırma çok zaman alabilir. OLE Microsoft Foundation Class Kitaplığı uyarlamasını tam özellikli, OLE özellikli uygulama yazmak için yapmanız gereken iş miktarını azaltmak için hedefidir.  
  
 Bu makalede MFC içinde uygulanan değil OLE API bölümlerini açıklanmaktadır. Windows SDK'sı OLE bölümüne ne uygulanır nasıl eşlendiğini tartışma de açıklanmaktadır.  
  
##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>Sınıf kitaplığı tarafından uygulanmadı OLE bölümlerini  
 Doğrudan birkaç arabirimleri ve OLE özelliklerini MFC tarafından sağlanmaz. Bu özellikleri kullanmak istiyorsanız, OLE API doğrudan çağırabilirsiniz.  
  
 IMoniker arabirimi  
 `IMoniker` Arabirimi sınıf kitaplığı tarafından uygulanan (örneğin, `COleServerItem` sınıfı) daha önce Programcı gösterilmeyen ancak. Bu arabirimi hakkında daha fazla bilgi için OLE ad uygulamaları Windows SDK'ın OLE bölümünde bakın. Ancak, aynı zamanda bkz [CMonikerFile](../mfc/reference/cmonikerfile-class.md) ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).  
  
 IUnknown ve IMarshal arabirimi  
 **IUnknown** arabirimi sınıf kitaplığı tarafından uygulanan ancak Programcı gösterilmez. **IMarshal** arabirimi sınıf kitaplığı tarafından uygulanmadı ancak dahili olarak kullanılır. Sınıf kitaplığı zaten kullanılarak oluşturulan otomasyon sunucuları yerleşik özellikleri hazırlama vardır.  
  
 Veri dosyalarını yazmak (bileşik dosyaları)  
 Bileşik dosyalar kısmen sınıf kitaplığı tarafından desteklenir. Bileşik dosyalar oluşturma ötesinde doğrudan yönlendirme işlevleri hiçbiri desteklenmiyor. MFC sınıf kullanan **COleFileStream** standart dosya işlevlerle akışları işlenmesini desteklemek için. Daha fazla bilgi için bkz: [kapsayıcılar: bileşik dosyalar](../mfc/containers-compound-files.md).  
  
 İşlem içi sunucuları ve nesne işleyicileri  
 İşlem içi sunucuları ve nesne işleyicileri görsel düzenleme verilerini veya bir dinamik bağlantı kitaplığı (DLL) tam Bileşen Nesne Modeli (COM) nesnelerini uyarlamasını izin verir. Bunu yapmak için OLE API doğrudan çağırarak DLL uygulayabilirsiniz. Ancak, bir Otomasyon sunucusu yazıyorsanız ve kullanıcı arabirimi olmadan sunucunuz varsa, sunucunuz bir işlemdeki sunucu yapıp tamamen bir DLL içine koyabilirsiniz AppWizard kullanabilirsiniz. Bu konular hakkında daha fazla bilgi için bkz: [otomasyon sunucuları](../mfc/automation-servers.md).  
  
> [!TIP]
>  Otomasyon sunucusu uygulamak için en kolay yolu, onu DLL'de yerleştirmektir. MFC bu yaklaşım destekler.  
  
 MFC teknik Notları Microsoft Foundation OLE sınıfları OLE arabirimleri nasıl uygulamak daha fazla bilgi için bkz: [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), ve [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [OLE arka planı](../mfc/ole-background.md)   
 [OLE Arka Planı: Uygulama Stratejileri](../mfc/ole-background-implementation-strategies.md)

