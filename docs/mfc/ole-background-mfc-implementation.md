---
title: 'OLE Arka Planı: MFC Uygulaması'
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
ms.openlocfilehash: 1dffdafbd02697db5aec341fec253c84217a0faf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619871"
---
# <a name="ole-background-mfc-implementation"></a>OLE Arka Planı: MFC Uygulaması

Ham OLE API 'sinin boyutu ve karmaşıklığı nedeniyle doğrudan OLE uygulamaları yazmak için çağırmak çok uzun sürebilir. OLE Microsoft Foundation Class Kitaplığı uygulamasının amacı, tam özellikli, OLE özellikli uygulamalar yazmak için yapmanız uygun iş miktarını azaltmaktır.

Bu makalede, OLE API 'sinin MFC içinde uygulanmamış kısımları açıklanmaktadır. Tartışmada ayrıca, Windows SDK OLE bölümüne nasıl uygulandığı açıklanır.

## <a name="portions-of-ole-not-implemented-by-the-class-library"></a><a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>OLE 'nin bölümleri sınıf kitaplığı tarafından uygulanmadı

OLE 'nin birkaç arabirimi ve özelliği doğrudan MFC tarafından sağlanmamıştır. Bu özellikleri kullanmak istiyorsanız, OLE API 'sini doğrudan çağırabilirsiniz.

IMoniker arabirimi `IMoniker` arabirim, sınıf kitaplığı tarafından uygulanır (örneğin, `COleServerItem` sınıfı), ancak daha önce programcıya gösterilmez. Bu arabirim hakkında daha fazla bilgi için, Windows SDK OLE bölümünde OLE bilinen ad uygulamaları bölümüne bakın. Ancak bkz. Class [CMonikerFile](reference/cmonikerfile-class.md) and [CAsyncMonikerFile](reference/casyncmonikerfile-class.md).

IUnknown ve IComparer arabirimleri `IUnknown` arabirimi sınıf kitaplığı tarafından uygulanır, ancak programcıya gösterilmez. `IMarshal`Arabirim, sınıf kitaplığı tarafından uygulanmıyor, ancak dahili olarak kullanılıyor. Sınıf kitaplığı kullanılarak oluşturulan Otomasyon sunucularında, içinde yerleşik sıralama özellikleri zaten var.

Docfiles (bileşik dosyalar) Birleşik dosyalar, sınıf kitaplığı tarafından kısmen desteklenir. Bileşik dosyaları oluşturma ötesinde doğrudan işleyen işlevlerden hiçbiri desteklenir. MFC `COleFileStream` , standart dosya işlevleriyle akışların işlenmesini desteklemek için sınıfını kullanır. Daha fazla bilgi için bkz. [kapsayıcı: bileşik dosyalar](containers-compound-files.md).

İşlem içi sunucular ve nesne Işleyicileri işlem içi sunucular ve nesne işleyicileri, dinamik bir bağlantı kitaplığındaki (DLL) görsel veri nesnesi veya tam bileşen nesne modeli (COM) nesnelerinin uygulanmasına izin verir. Bunu yapmak için, OLE API 'sini doğrudan çağırarak DLL 'nizi uygulayabilirsiniz. Ancak, bir Otomasyon sunucusu yazıyorsanız ve sunucunuzun kullanıcı arabirimi yoksa, uygulamanızın işlem içi bir sunucu olmasını ve tamamen bir DLL 'ye koyabilmeniz için AppWizard 'ı kullanabilirsiniz. Bu konular hakkında daha fazla bilgi için bkz. [Automation Servers](automation-servers.md).

> [!TIP]
> Otomasyon sunucusunu uygulamanın en kolay yolu bir DLL 'ye yerleştirmelidir. MFC bu yaklaşımı destekler.

Microsoft Foundation OLE sınıflarının OLE arabirimlerini nasıl uygulayan hakkında daha fazla bilgi için bkz. MFC teknik notları [38](tn038-mfc-ole-iunknown-implementation.md), [39](tn039-mfc-ole-automation-implementation.md)ve [40](tn040-mfc-ole-in-place-resizing-and-zooming.md).

## <a name="see-also"></a>Ayrıca bkz.

[OLE arka planı](ole-background.md)<br/>
[OLE Arka Planı: Uygulama Stratejileri](ole-background-implementation-strategies.md)
