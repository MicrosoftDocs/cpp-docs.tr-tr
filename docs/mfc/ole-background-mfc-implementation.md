---
title: 'OLE arka planı: MFC uygulaması'
ms.date: 11/04/2016
f1_keywords:
- IMarshall
- IMoniker
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
ms.openlocfilehash: f793c7d7303a49057e46c32eb658ea7eea8e9ccc
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57267283"
---
# <a name="ole-background-mfc-implementation"></a>OLE arka planı: MFC uygulaması

Boyutu ve ham OLE API karmaşıklığı nedeniyle doğrudan OLE uygulamaları yazmak için çağırma çok zaman alıcı olabilir. Microsoft Foundation Class Kitaplığı uygulaması OLE tam özellikli, OLE özellikli uygulamaları yazmak için yapmanız gereken iş miktarını azaltmak için hedefidir.

Bu makalede, MFC içinde uygulanan değil OLE API bölümlerini açıklar. Tartışma de Windows SDK'sı OLE bölümüne ne uygulanan nasıl eşlendiğini açıklanır.

##  <a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a> OLE sınıf kitaplığının uygulanmadı bölümleri

Doğrudan birkaç arabirimleri ve özelliklerinin OLE MFC tarafından sağlanmaz. Bu özellikleri kullanmak istiyorsanız, OLE API'sini doğrudan çağırabilir.

IMoniker arabirimi `IMoniker` arabirimi, sınıf kitaplığı tarafından uygulanır (örneğin, `COleServerItem` sınıfı) ancak daha önce programcıya sunulmamıştır. Bu arabirim hakkında daha fazla bilgi için OLE ad uygulamalarını Windows SDK'sı OLE bölümünde bakın. Ancak, sınıfına bakın [CMonikerFile](../mfc/reference/cmonikerfile-class.md) ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md).

IUnknown ve IMarshal arabirimi `IUnknown` arabirimi sınıf kitaplığı tarafından uygulanır, ancak programcıya gösterilmez. `IMarshal` Arabirimi sınıf kitaplığının uygulanmadı ancak dahili olarak kullanılır. Sınıf kitaplığı zaten kullanılarak oluşturulan otomasyon sunucuları hazırlama özellikleri yerleşik olarak sahip.

Veri dosyalarını yazmak (bileşik dosyaları) bileşik dosyalar sınıf kitaplığının kısmen desteklenir. Bileşik dosyalar oluşturma ötesinde doğrudan düzenlemezsiniz işlevleri hiçbiri desteklenmiyor. MFC kullanan sınıf `COleFileStream` standart dosya işlevleri akışlarla işlenmesini desteklemek için. Daha fazla bilgi için bkz [kapsayıcıları: Bileşik dosyalar](../mfc/containers-compound-files.md).

İşlem içi sunucular ve nesne işleyicileri işlem içi sunucular ve nesne işleyicileri görsel düzenleme verileri veya bir dinamik bağlantı kitaplığı (DLL) tam Bileşen Nesne Modeli (COM) nesneleri uygulamasına izin. Bunu yapmak için OLE API'sini doğrudan çağırmak DLL dosyanızı uygulayabilirsiniz. Ancak, Otomasyon sunucusu yazıyorsanız ve hiçbir kullanıcı arabirimi sunucunuz varsa sunucunuza bir işlem sunucusu ve tamamen bir DLL içine koyabilirsiniz AppWizard kullanabilirsiniz. Bu konular hakkında daha fazla bilgi için bkz. [otomasyon sunucuları](../mfc/automation-servers.md).

> [!TIP]
>  Otomasyon sunucusu uygulamak için en kolay yolu, onu bir DLL içinde yerleştirmektir. Bu yaklaşım MFC destekler.

Microsoft Foundation OLE sınıfları OLE arabirimleri nasıl uygulamak daha fazla bilgi için bkz. MFC teknik notları [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md), ve [40](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="see-also"></a>Ayrıca bkz.

[OLE Arka Planı](../mfc/ole-background.md)<br/>
[OLE arka planı: Uygulama stratejileri](../mfc/ole-background-implementation-strategies.md)
