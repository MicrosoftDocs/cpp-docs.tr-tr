---
title: CSocketFile sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 3b969f81c0c6e1868a66aeaa1c4d9339792062df
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69502457"
---
# <a name="csocketfile-class"></a>CSocketFile sınıfı

Windows `CFile` yuvaları aracılığıyla bir ağ üzerinden veri göndermek ve almak için kullanılan bir nesne.

## <a name="syntax"></a>Sözdizimi

```
class CSocketFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CSocketFile:: CSocketFile](#csocketfile)|Bir `CSocketFile` nesnesi oluşturur.|

## <a name="remarks"></a>Açıklamalar

Bu amaçla nesnesini `CSocket` nesnesine `CSocketFile` ekleyebilirsiniz. Ayrıca, `CSocketFile` MFC serileştirme kullanarak veri göndermeyi ve almayı basitleştirmek için nesnesini bir `CArchive` nesnesine ekleyebilirsiniz.

Verileri seri hale getirmek (göndermek) için, `CSocketFile` `CSocket` nesnesine veri yazmak için üye işlevleri çağıran arşive eklersiniz. Veri serisini kaldırmak (almak) için arşivden ayıklayın. Bu, arşivin `CSocket` nesneden veri `CSocketFile` okumak için üye işlevleri çağırmasını sağlar.

> [!TIP]
>  Burada açıklandığı `CSocketFile` gibi kullanmanın yanı sıra, bunu tek başına bir dosya nesnesi olarak kullanabilirsiniz; örneğin `CFile`, temel sınıfı. Ayrıca, arşiv tabanlı `CSocketFile` herhangi bir MFC serileştirme işlevleriyle de kullanabilirsiniz. Tüm işlevlerini desteklemediğinden, bazı varsayılan MFC serileştirme işlevleri ile `CSocketFile`uyumlu değildir. `CFile` `CSocketFile` Bu, `CEditView` sınıfının özellikle de doğrudur. `CEditView` `CArchive` `CEditView::Serialize` Kullanarak bir nesneye`CSocketFile` eklenen bir nesne aracılığıyla veri serileştirmenize çalışmayın; bunun yerine kullanın. `CEditView::SerializeRaw` İşlevi dosya nesnesinin `Seek` ,`CSocketFile` gibi işlevleri olmasını bekler. `SerializeRaw`

`CArchive` Ve `CSocketFile` `PumpMessages(FD_READ)` `CSocket::Receive` ile kullandığınızda ,istenenbaytmiktarınıbekleyenbirdöngüye(by)girenbirdurumlakarşılaşabilirsiniz.`CSocket` Bunun nedeni, Windows Yuvaları fd_read bildirimi başına yalnızca bir alma çağrısına izin ver, `CSocketFile` ancak `CSocket` fd_read başına birden fazla alma çağrısına izin veriyor. Okunacak bir veri olmadığında bir FD_READ alırsanız uygulama askıda kalır. Başka bir FD_READ yoksa, uygulama yuva üzerinden iletişim kurmasını durduruyor.

Bu sorunu aşağıdaki şekilde çözebilirsiniz. Yuva sınıfınızın `CAsyncSocket::IOCtl(FIONREAD, ...)` `Serialize` yönteminde, yuvadan okunan beklenen veriler bir TCP paketinin boyutunu aştığında ileti sınıfınızın yöntemini çağırmadan önce çağırın (ağ ortamının maksimum iletim birimi). `OnReceive` genellikle en az 1096 bayt). Kullanılabilir verilerin boyutu gerekenden küçükse, tüm verilerin alınmasını bekleyin ve sonra okuma işlemini başlatın.

Aşağıdaki örnekte, `m_dwExpected` kullanıcının almayı beklediği yaklaşık bayt sayısıdır. Kodunuzun başka bir yerinde bildirdiğiniz varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Daha fazla bilgi için bkz. [MFC 'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), [Windows Yuvaları: ](../../mfc/windows-sockets-using-sockets-with-archives.md) [Windows Sockets 2 API](/windows/win32/WinSock/windows-sockets-start-page-2)ve arşiv ile yuvaları kullanma.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock. h

##  <a name="csocketfile"></a>CSocketFile:: CSocketFile

Bir `CSocketFile` nesnesi oluşturur.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pSocket*<br/>
`CSocketFile` Nesneye iliştirilecek yuva.

*bArchiveCompatible*<br/>
Dosya nesnesinin bir `CArchive` nesneyle kullanılıp kullanılmayacağını belirtir. Yalnızca tek başına bir `CSocketFile` `CFile` nesne gibi tek başına bir nesne olarak kullanmak istediğiniz gibi, belirli sınırlamalara sahip bir nesneyi kullanmak istiyorsanız yanlış geçirin. Bu bayrak, nesnesine eklenen `CArchive` `CSocketFile` nesnenin, okuma için arabelleğini yönetme şeklini değiştirir.

### <a name="remarks"></a>Açıklamalar

Nesne kapsam dışına geçtiğinde veya silindiğinde, nesnenin yıkıcısı kendisini yuva nesnesinden ilişkilendirir.

> [!NOTE]
>  Bir `CSocketFile` nesnesi`CArchive` olmayan (sınırlı) dosya olarak da kullanılabilir. Varsayılan olarak, `CSocketFile` oluşturucunun *bArchiveCompatible* parametresi true 'dur. Bu, dosya nesnesinin bir arşiv ile kullanılmak üzere olduğunu belirtir. Dosya nesnesini arşiv olmadan kullanmak için, *bArchiveCompatible* parametresine yanlış geçirin.

"Arşiv uyumlu" modunda bir `CSocketFile` nesne daha iyi performans sağlar ve bir "kilitlenme" düzeyini azaltır. Hem gönderme hem de alma yuvaları birbirini beklerken veya ortak bir kaynak için bir kilitlenme oluşur. Bu durum, `CArchive` nesne bir `CFile` nesneyle aynı şekilde çalıştığında `CSocketFile` meydana gelebilir. İle `CFile`arşiv, istenenden daha az bayt alırsa, dosyanın sonuna ulaşıldığını varsayabilir.

`CSocketFile`Ancak, veriler ileti tabanlıdır; arabellekte birden çok ileti bulunabilir, bu nedenle istenen bayt sayısından daha az sayıda alma işlemi dosya sonunu göstermez. Uygulama `CFile`, bu durumda olabileceği gibi engellemez ve arabellek boşalıncaya kadar arabellekteki iletileri okumaya devam edebilir. [CArchive:: IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) işlevi, bu tür bir durumda arşiv arabelleğinin durumunu izlemek için yararlıdır.

Kullanımı `CSocketFile`hakkında daha fazla bilgi için, bkz [. Windows Yuvaları: Arşivleri](../../mfc/windows-sockets-using-sockets-with-archives.md) ve[Windows yuvaları ile yuvaları kullanma: Arşivleri](../../mfc/windows-sockets-example-of-sockets-using-archives.md)kullanan yuvalar örneği.

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)
