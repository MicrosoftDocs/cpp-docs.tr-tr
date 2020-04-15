---
title: Csocketfile Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
ms.openlocfilehash: 83810a05925e5c8302240b61d95c131fdd78b426
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81318169"
---
# <a name="csocketfile-class"></a>Csocketfile Sınıfı

Windows `CFile` Soketleri üzerinden ağ üzerinden veri göndermek ve almak için kullanılan bir nesne.

## <a name="syntax"></a>Sözdizimi

```
class CSocketFile : public CFile
```

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CSocketFile::CSocketFile](#csocketfile)|Bir `CSocketFile` nesne inşa eder.|

## <a name="remarks"></a>Açıklamalar

Bu amaçla `CSocketFile` nesneyi `CSocket` bir nesneye ekleyebilirsiniz. Ayrıca, MFC serileştirme kullanarak `CSocketFile` veri `CArchive` gönderme ve alma basitleştirmek için nesneyi bir nesneye ekleyebilirsiniz ve genellikle yapabilirsiniz.

Verileri serihale getirmek (göndermek) için, üye işlevleri `CSocketFile` `CSocket` nesneye veri yazmaya çağıran arşive eklersiniz. Verileri deserialize etmek (almak) için arşivden ayıklarsınız. Bu, arşivin `CSocketFile` nesneden verileri okumak `CSocket` için üye işlevleri çağırmasına neden olur.

> [!TIP]
> Burada `CSocketFile` açıklandığı gibi kullanmanın yanı sıra, taban sınıfı ile `CFile`olduğu gibi, tek başına bir dosya nesnesi olarak kullanabilirsiniz. Arşiv tabanlı `CSocketFile` MFC serileştirme işlevlerini de kullanabilirsiniz. 'ın tüm işlevlerini `CSocketFile` desteklemediği için, bazı varsayılan MFC serileştirme işlevleri ile `CSocketFile`uyumlu değildir. `CFile` Bu özellikle `CEditView` sınıf için geçerlidir. Kullanarak `CEditView` bir `CArchive` `CSocketFile` nesneye bağlı bir nesne aracılığıyla verileri `CEditView::SerializeRaw`serihale getirmeye çalışmamalısınız; bunun `CEditView::Serialize` yerine kullanın. İşlev, `SerializeRaw` dosya nesnesinin , `Seek`sahip `CSocketFile` olmayan işlevlere sahip olmasını bekler.

`CArchive` Kullandığınızda `CSocketFile` ve `CSocket`, istenilen bayt `CSocket::Receive` miktarını bekleyen bir `PumpMessages(FD_READ)`döngü (by) girer bir durumla karşılaşabilirsiniz. Bunun nedeni, `CSocketFile` Windows soketlerinin FD_READ bildirimi başına yalnızca `CSocket` bir recv araması ve FD_READ başına birden çok recv araması izni sağlamasıdır. Okunacak veri olmadığında FD_READ alırsanız, uygulama askıda kalır. Başka bir FD_READ alamazsanız, uygulama soket üzerinden iletişimi durdurur.

Bu sorunu aşağıdaki gibi çözebilirsiniz. Soket `OnReceive` sınıfının yönteminde, `CAsyncSocket::IOCtl(FIONREAD, ...)` soketten `Serialize` okunması beklenen veriler bir TCP paketinin boyutunu aştığında (genellikle en az 1096 bayt olan ağ ortamının maksimum iletim birimi) ileti sınıfının yöntemini aramadan önce arayın. Kullanılabilir verilerin boyutu gerekenden daha azsa, tüm verilerin alınmasını bekleyin ve ancak o zaman okuma işlemini başlatın.

Aşağıdaki örnekte, `m_dwExpected` kullanıcının almayı beklediği yaklaşık bayt sayısıdır. Kodunuzun başka bir yerinde beyan ettiğiniz varsayılır.

[!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]

Daha fazla bilgi için, [MFC'deki Windows Soketleri,](../../mfc/windows-sockets-in-mfc.md) [Windows Soketleri: Arşivli Soketleri kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md)nın yanı sıra [Windows Soketleri 2 API'ye](/windows/win32/WinSock/windows-sockets-start-page-2)bakın.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

[Cobject](../../mfc/reference/cobject-class.md)

[Cfile](../../mfc/reference/cfile-class.md)

`CSocketFile`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** afxsock.h

## <a name="csocketfilecsocketfile"></a><a name="csocketfile"></a>CSocketFile::CSocketFile

Bir `CSocketFile` nesne inşa eder.

```
explicit CSocketFile(
    CSocket* pSocket,
    BOOL bArchiveCompatible = TRUE);
```

### <a name="parameters"></a>Parametreler

*pSoket*<br/>
`CSocketFile` Nesneye takacak soket.

*bArchiveUyumlu*<br/>
Dosya nesnesinin bir `CArchive` nesneyle kullanılmak üzere olup olmadığını belirtir. Yalnızca nesneyi `CSocketFile` tek başına kullanmak istiyorsanız, belirli sınırlamalarla tek başına `CFile` bir nesne gibi FALSE'u geçirin. Bu bayrak, `CArchive` `CSocketFile` nesneye bağlı nesnenin okuma arabelleği nasıl yönetir değiştirir.

### <a name="remarks"></a>Açıklamalar

Nesne kapsam dışına çıktığında veya silindiğinde nesnenin yıkıcısı kendisini soket nesnesinden ayırıyor.

> [!NOTE]
> A, `CSocketFile` `CArchive` nesne olmadan (sınırlı) bir dosya olarak da kullanılabilir. Varsayılan olarak, `CSocketFile` oluşturucubArchiveCompatible parametresi TRUE'dur. *bArchiveCompatible* Bu, dosya nesnesinin bir arşivle kullanılmak üzere olduğunu belirtir. Arşiv olmadan dosya nesnesini kullanmak için *bArchiveCompatible* parametresinde FALSE'u geçirin.

"Arşiv uyumlu" modunda, `CSocketFile` bir nesne daha iyi performans sağlar ve bir "kilitlenme" tehlikesini azaltır. Hem gönderme hem de alma soketleri birbirini beklerken veya ortak bir kaynak için kilitlenme oluşur. `CArchive` Nesne bir `CSocketFile` `CFile` nesneyle çalıştığı gibi çalışıyorsa, bu durum oluşabilir. `CFile`Bununla birlikte, arşiv, istediği bayttan daha az bayt alırsa, dosyanın sonuna ulaşıldığını varsayabilir.

Bununla `CSocketFile`birlikte, veri ileti tabanlıdır; arabellek birden çok ileti içerebilir, bu nedenle istenen bayt sayısından daha az almak dosyasonu anlamına gelmez. Uygulama bu durumda olduğu gibi `CFile`engellemez ve arabellek boş alana kadar arabellekten gelen iletileri okumaya devam edebilir. [CArchive::IsBufferBoş](../../mfc/reference/carchive-class.md#isbufferempty) işlevi böyle bir durumda arşiv arabelleği durumunu izlemek için yararlıdır.

Kullanımı hakkında daha fazla `CSocketFile`bilgi için, makalelerWindows Soketleri bakınız: Arşiv ve Windows Soketleri [ile Soketler kullanma:](../../mfc/windows-sockets-using-sockets-with-archives.md) [Arşiv kullanarak Soketler Örneği](../../mfc/windows-sockets-example-of-sockets-using-archives.md).

## <a name="see-also"></a>Ayrıca bkz.

[CFile Sınıfı](../../mfc/reference/cfile-class.md)<br/>
[Hiyerarşi Grafiği](../../mfc/hierarchy-chart.md)<br/>
[CAsyncSocket Sınıfı](../../mfc/reference/casyncsocket-class.md)<br/>
[CSocket Sınıfı](../../mfc/reference/csocket-class.md)
