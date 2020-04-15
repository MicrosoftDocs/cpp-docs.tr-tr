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
ms.openlocfilehash: 25c98c3683a8656bb5188f22d0464d25a4901f49
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364525"
---
# <a name="ole-background-mfc-implementation"></a>OLE Arka Planı: MFC Uygulaması

Ham OLE API boyutu ve karmaşıklığı nedeniyle, doğrudan OLE uygulamaları yazmak için arama çok zaman alıcı olabilir. OLE'nin Microsoft Foundation Class Library uygulamasının amacı, tam özellikli, OLE özellikli uygulamaları yazmak için yapmanız gereken iş miktarını azaltmaktır.

Bu makalede, OLE API'nin MFC içinde uygulanmamış bölümleri açıklanmaktadır. Tartışma ayrıca, Windows SDK'nın OLE bölümüne uygulanan haritaların nasıl uygulandığını da açıklar.

## <a name="portions-of-ole-not-implemented-by-the-class-library"></a><a name="_core_portions_of_ole_not_implemented_by_the_class_library"></a>Sınıf Kitaplığı Tarafından Uygulanmayan OLE Bölümleri

OLE'nin birkaç arabirimi ve özelliği doğrudan MFC tarafından sağlanmaz. Bu özellikleri kullanmak istiyorsanız, Doğrudan OLE API'yi arayabilirsiniz.

IMoniker Arabirimi `IMoniker` Arabirimi sınıf kitaplığı (örneğin, `COleServerItem` sınıf) tarafından uygulanır, ancak daha önce programcıya maruz kalmamıştır. Bu arabirim hakkında daha fazla bilgi için Windows SDK'nın OLE bölümündeki OLE Takma Uygulama bölümüne bakın. Ancak, ayrıca [sınıf CMonikerFile](../mfc/reference/cmonikerfile-class.md) ve [CAsyncMonikerFile](../mfc/reference/casyncmonikerfile-class.md)bakın.

IUnknown ve IMarshal `IUnknown` Arabirimleri Arabirimi sınıf kitaplığı tarafından uygulanır, ancak programcıya açık değildir. Arabirim `IMarshal` sınıf kitaplığı tarafından uygulanmaz, ancak dahili olarak kullanılır. Sınıf kitaplığı kullanılarak oluşturulmuş otomasyon sunucuları zaten yerleşik mareşalleme yeteneklerine sahiptir.

Docfiles (Bileşik Dosyalar) Bileşik dosyaları kısmen sınıf kitaplığı tarafından desteklenir. Bileşik dosyaları oluşturmanın ötesinde doğrudan işleyen işlevlerin hiçbiri desteklenmez. MFC, `COleFileStream` standart dosya işlevlerine sahip akışların manipülasyonuna destek vermek için sınıfı kullanır. Daha fazla bilgi için, makale [Kapsayıcılar bakın: Bileşik Dosyalar](../mfc/containers-compound-files.md).

İşlem İçi Sunucular ve Nesne İşleyicileri İşlem Içi sunucular ve nesne işleyicileri, dinamik bağlantı kitaplığında (DLL) görsel düzenleme verilerinin veya tam Bileşen Nesne Modeli (COM) nesnelerinin uygulanmasına olanak tanır. Bunu yapmak için, Doğrudan OLE API'yi arayarak DLL'nizi uygulayabilirsiniz. Ancak, bir Otomasyon sunucusu yazıyorsanız ve sunucunuzda kullanıcı arabirimi yoksa, sunucunuzu işlem içi sunucu yapmak ve tamamen bir DLL'ye koymak için AppWizard'ı kullanabilirsiniz. Bu konular hakkında daha fazla bilgi için [Otomasyon Sunucuları'na](../mfc/automation-servers.md)bakın.

> [!TIP]
> Bir Otomasyon sunucusunu uygulamanın en kolay yolu, sunucuyu bir DLL'ye yerleştirmektir. MFC bu yaklaşımı destekler.

Microsoft Foundation OLE sınıflarının OLE arabirimlerini nasıl uyguladığı hakkında daha fazla bilgi için MFC Teknik Notlar [38](../mfc/tn038-mfc-ole-iunknown-implementation.md), [39](../mfc/tn039-mfc-ole-automation-implementation.md)ve [40'a](../mfc/tn040-mfc-ole-in-place-resizing-and-zooming.md)bakın.

## <a name="see-also"></a>Ayrıca bkz.

[OLE Arka Plan](../mfc/ole-background.md)<br/>
[OLE Arka Planı: Uygulama Stratejileri](../mfc/ole-background-implementation-strategies.md)
