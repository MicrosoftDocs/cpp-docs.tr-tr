---
title: CSocketFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSocketFile
- AFXSOCK/CSocketFile
- AFXSOCK/CSocketFile::CSocketFile
dev_langs:
- C++
helpviewer_keywords:
- CSocketFile [MFC], CSocketFile
ms.assetid: 7924c098-5f72-40d6-989d-42800a47958f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0e3bf8d9ee58143e7a96b85174e4533b3c2e50ec
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33372641"
---
# <a name="csocketfile-class"></a>CSocketFile sınıfı
A `CFile` göndermek ve Windows Yuvaları aracılığıyla bir ağ üzerinden veri almak için kullanılan nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|Oluşturan bir `CSocketFile` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ekleyebilir miyim `CSocketFile` nesnesine bir `CSocket` bu amaç için nesne. Ayrıca ve genellikle ekleyin `CSocketFile` nesnesine bir `CArchive` MFC serileştirme kullanarak veri gönderme ve alma basitleştirmek için nesne.  
  
 (Gönderme) verilerini seri hale getirmek için çağıran arşivine eklemeden `CSocketFile` veri yazmak için üye işlevleri `CSocket` nesnesi. Seri durumdan çıkarılacak (Al) verileri arşivden ayıklayın. Bu çağırmak arşiv neden `CSocketFile` verileri okumak için üye işlevleri `CSocket` nesnesi.  
  
> [!TIP]
>  Kullanarak yanı sıra `CSocketFile` ile yapabildiğiniz gibi burada açıklandığı gibi bir tek başına dosya nesnesi olarak kullanabileceğiniz `CFile`, kendi temel sınıfı. Aynı zamanda `CSocketFile` arşiv tabanlı MFC serileştirme işlevlere sahip. Çünkü `CSocketFile` tüm desteklemiyor `CFile`kullanıcının işlevselliği, bazı varsayılan MFC Seri işlevleri ile uyumlu olmadığında `CSocketFile`. Bu özellikle, geçerlidir `CEditView` sınıfı. Değil seri denemelisiniz `CEditView` verilerine bir `CArchive` nesne iliştirilmiş bir `CSocketFile` kullanarak nesne `CEditView::SerializeRaw`; kullanın **CEditView::Serialize** yerine. `SerializeRaw` İşlev, İşlevler, sahip için dosya nesnesi bekliyor `Seek`, o `CSocketFile` sahip değil.  
  
 Kullandığınızda `CArchive` ile `CSocketFile` ve `CSocket`, bir durum karşılaşabilirsiniz nerede **CSocket::Receive** bir döngüye girer (tarafından **PumpMessages(FD_READ)**) bekleniyor İstenen bayt miktarı. Windows Yuvaları FD_READ bildirim başına yalnızca bir Al çağrısı izin Bunun nedeni, ancak `CSocketFile` ve `CSocket` FD_READ başına birden çok alınması çağrılarının izin verir. Okunacak veri yok olduğunda bir FD_READ alırsanız, uygulama askıda kalır. Hiçbir zaman başka bir FD_READ alırsanız, uygulama yuvası üzerinden iletişim kurmasını durdurur.  
  
 Bu sorun aşağıdaki gibi çözülebilir. İçinde `OnReceive` yöntemi sınıfınızın yuva çağrısı **CAsyncSocket::IOCtl (FIONREAD,...)**  çağırmadan önce `Serialize` yuvadan okumak için beklenen veri bir TCP paketi (ağ ortamının, genellikle en az 1096 bayt en büyük iletim birimi) boyutunu aşarsa, ileti sınıfı yöntemi. Kullanılabilir veri boyutu gereken daha az ise, alınması ve ardından yalnızca okuma işlemi başlatmak tüm veriler için bekleyin.  
  
 Aşağıdaki örnekte, `m_dwExpected` yaklaşık almak için kullanıcı bekliyor bayt sayısıdır. Başka bir yerde kodunuzda bildirirken olduğunu varsayılır.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Daha fazla bilgi için bkz: [MFC'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md), yanı [Windows Sockets 2 API](http://msdn.microsoft.com/library/windows/desktop/ms740673).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsock.h  
  
##  <a name="csocketfile"></a>  CSocketFile::CSocketFile  
 Oluşturan bir `CSocketFile` nesnesi.  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSocket`  
 Eklemek için yuva `CSocketFile` nesnesi.  
  
 `bArchiveCompatible`  
 Dosya nesnesi ile kullanılmak üzere olup olmadığını belirtir bir `CArchive` nesnesi. Geçirmek **FALSE** yalnızca kullanmak istiyorsanız `CSocketFile` tek başına gibi tek başına bir biçimde nesne `CFile` nesne, belirli sınırlamalarla birlikte. Bu bayrak değişiklikleri nasıl `CArchive` nesne iliştirilmiş `CSocketFile` nesnesi arabelleğini okumak için yönetir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne kapsam dışında gider ya da silinir nesnenin yıkıcı kendisini yuva nesnesinden keser.  
  
> [!NOTE]
>  A `CSocketFile` (sınırlı) dosyası olarak da kullanılabilir bir `CArchive` nesnesi. Varsayılan olarak, `CSocketFile` Oluşturucusu'nın `bArchiveCompatible` parametresi **doğru**. Bu dosya nesnesi bir arşiv ile kullanılmak üzere olduğunu belirtir. Bir arşiv olmadan dosya nesnesi kullanmak için geçirmek **FALSE** içinde `bArchiveCompatible` parametresi.  
  
 Kendi "Arşiv uyumlu" modunda bir `CSocketFile` nesne daha iyi performans sağlar ve bir "kilitlenme." tehlike azaltır Gönderme ve alma yuva birbirlerine ya da ortak bir kaynak için bekleyen bir kilitlenme oluşur. Bu durum oluşabilir `CArchive` nesne çalıştığınız `CSocketFile` mu ile yolu bir `CFile` nesnesi. İle `CFile`, Arşiv, istenenden daha az sayıda bayt alırsa, dosya sonuna ulaşıldı varsayabilirsiniz.  
  
 İle `CSocketFile`ancak, veri tabanlı ileti; arabellek birden fazla ileti içerebilir, bu nedenle istenen bayt sayısından az alma değil kapsıyor dosya sonu. Sahip olabileceği gibi bu durumda uygulamayı engellemez `CFile`, ve arabellek boş olana kadar arabellekteki iletileri okumak devam edebilirsiniz. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) işlevi arşiv 's arabellek böyle bir durumda durumunu izlemek için yararlıdır.  
  
 Kullanımı hakkında daha fazla bilgi için `CSocketFile`, makalelerine bakın [Windows Yuvaları: arşivlerle kullanılan yuvalara](../../mfc/windows-sockets-using-sockets-with-archives.md) ve [Windows Yuvaları: örnek, yuva kullanarak arşivler](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)   
 [CSocket Sınıfı](../../mfc/reference/csocket-class.md)
