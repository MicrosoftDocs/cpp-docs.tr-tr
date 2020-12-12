---
description: 'Daha fazla bilgi edinin: CSocketFile sınıfı'
title: CSocketFile sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 4ca484545e11502a11acf5f27b00ee2df49fc9d6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318656"
---
# <a name="csocketfile-class"></a>CSocketFile sınıfı

`CFile`Windows Yuvaları aracılığıyla bir ağ üzerinden veri göndermek ve almak için kullanılan bir nesne.

## <a name="syntax"></a>Syntax

```
class CSocketFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSocketFile:: CSocketFile](#csocketfile)|Bir `CSocketFile` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

`CSocketFile` `CSocket` Bu amaçla nesnesini nesnesine ekleyebilirsiniz. Ayrıca, `CSocketFile` `CArchive` MFC serileştirme kullanarak veri göndermeyi ve almayı basitleştirmek için nesnesini bir nesnesine ekleyebilirsiniz.

Verileri seri hale getirmek (göndermek) için, `CSocketFile` nesnesine veri yazmak için üye işlevleri çağıran arşive eklersiniz `CSocket` . Veri serisini kaldırmak (almak) için arşivden ayıklayın. Bu, arşivin `CSocketFile` nesneden veri okumak için üye işlevleri çağırmasını sağlar `CSocket` .

> [!TIP]
> Burada açıklandığı gibi kullanmanın yanı sıra, `CSocketFile` bunu tek başına bir dosya nesnesi olarak kullanabilirsiniz; örneğin `CFile` , temel sınıfı. Ayrıca, `CSocketFile` Arşiv tabanlı herhangi BIR MFC serileştirme işlevleriyle de kullanabilirsiniz. `CSocketFile`Tüm `CFile` işlevlerini desteklemediğinden, bazı varsayılan MFC serileştirme işlevleri ile uyumlu değildir `CSocketFile` . Bu, sınıfının özellikle de doğrudur `CEditView` . `CEditView`Kullanarak bir nesneye eklenen bir nesne aracılığıyla veri serileştirmenize çalışmayın `CArchive` `CSocketFile` `CEditView::SerializeRaw` ; `CEditView::Serialize` bunun yerine kullanın. `SerializeRaw`İşlevi dosya nesnesinin, gibi işlevleri olmasını bekler `Seek` `CSocketFile` .

`CArchive`Ve ile kullandığınızda `CSocketFile` `CSocket` , `CSocket::Receive` `PumpMessages(FD_READ)` istenen bayt miktarını bekleyen bir döngüye (by) giren bir durumla karşılaşabilirsiniz. Bunun nedeni, Windows Yuvaları FD_READ bildirimi başına yalnızca bir alma çağrısına izin ver, `CSocketFile` ancak `CSocket` fd_read başına birden çok alınan çağrıya izin verir. Okunacak veri olmadığında bir FD_READ alırsanız uygulama askıda kalır. Daha önce başka bir FD_READ alamazsanız, uygulama yuva üzerinden iletişim kurmasını durduruyor.

Bu sorunu aşağıdaki şekilde çözebilirsiniz. `OnReceive`Yuva sınıfınızın yönteminde, `CAsyncSocket::IOCtl(FIONREAD, ...)` `Serialize` yuvadan okunan beklenen veriler bir TCP paketinin boyutunu (genellikle en az 1096 bayt) aştığında, size ileti sınıfınızın yöntemini çağırmadan önce çağırın. Kullanılabilir verilerin boyutu gerekenden küçükse, tüm verilerin alınmasını bekleyin ve sonra okuma işlemini başlatın.

Aşağıdaki örnekte, `m_dwExpected` kullanıcının almayı beklediği yaklaşık bayt sayısıdır. Kodunuzun başka bir yerinde bildirdiğiniz varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Daha fazla bilgi için bkz. [MFC 'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), [Windows Yuvaları: Arşivlerle yuvalar kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md)ve [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2).

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock. h

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a> CSocketFile:: CSocketFile

Bir `CSocketFile` nesnesi oluşturur.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pSocket*<br/>
Nesneye iliştirilecek yuva `CSocketFile` .

*bArchiveCompatible*<br/>
Dosya nesnesinin bir nesneyle kullanılıp kullanılmayacağını belirtir `CArchive` . Yalnızca tek başına bir nesne gibi tek başına bir `CSocketFile` nesne olarak kullanmak istediğiniz gibi `CFile` , belirli sınırlamalara sahip bir nesneyi kullanmak istiyorsanız yanlış geçirin. Bu bayrak, nesnesine `CArchive` eklenen nesnenin, `CSocketFile` okuma için arabelleğini yönetme şeklini değiştirir.

### <a name="remarks"></a>Açıklamalar

Nesne kapsam dışına geçtiğinde veya silindiğinde, nesnenin yıkıcısı kendisini yuva nesnesinden ilişkilendirir.

> [!NOTE]
> Bir `CSocketFile` nesnesi olmayan (sınırlı) dosya olarak da kullanılabilir `CArchive` . Varsayılan olarak, `CSocketFile` oluşturucunun *bArchiveCompatible* parametresi true 'dur. Bu, dosya nesnesinin bir arşiv ile kullanılmak üzere olduğunu belirtir. Dosya nesnesini arşiv olmadan kullanmak için, *bArchiveCompatible* parametresine yanlış geçirin.

"Arşiv uyumlu" modunda bir `CSocketFile` nesne daha iyi performans sağlar ve bir "kilitlenme" düzeyini azaltır. Hem gönderme hem de alma yuvaları birbirini beklerken veya ortak bir kaynak için bir kilitlenme oluşur. Bu durum, `CArchive` nesne bir nesneyle aynı şekilde çalıştığında meydana gelebilir `CSocketFile` `CFile` . İle `CFile` Arşiv, istenenden daha az bayt alırsa, dosyanın sonuna ulaşıldığını varsayabilir.

`CSocketFile`Ancak, veriler ileti tabanlıdır; arabellekte birden çok ileti bulunabilir, bu nedenle istenen bayt sayısından daha az sayıda alma işlemi dosya sonunu göstermez. Uygulama, bu durumda olabileceği gibi engellemez `CFile` ve arabellek boşalıncaya kadar arabellekteki iletileri okumaya devam edebilir. [CArchive:: IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) işlevi, bu tür bir durumda arşiv arabelleğinin durumunu izlemek için yararlıdır.

Kullanımı hakkında daha fazla bilgi için `CSocketFile` , bkz. [Windows Yuvaları: arşivleri](../../mfc/windows-sockets-using-sockets-with-archives.md) ve Windows yuvaları ile yuvaları kullanma [: arşivleri kullanarak yuvalar örneği](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="see-also"></a>Ayrıca bkz.

[CFile sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket sınıfı](../../mfc/reference/csocket-class.md)
