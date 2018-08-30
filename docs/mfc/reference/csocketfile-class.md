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
ms.openlocfilehash: c4c74d1ab89c45b7871cf0b4fa0d8a6350bc1425
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209643"
---
# <a name="csocketfile-class"></a>CSocketFile sınıfı
A `CFile` göndermek ve ağ üzerinden Windows Sockets veri almak için kullanılan nesne.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSocketFile : public CFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSocketFile::CSocketFile](#csocketfile)|Oluşturur bir `CSocketFile` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 İliştirebilirsiniz `CSocketFile` nesnesini bir `CSocket` bu amaç için nesne. Ayrıca ve genellikle ekleme `CSocketFile` nesnesini bir `CArchive` MFC serileştirme kullanarak veri gönderme ve alma basitleştirmek için nesne.  
  
 (Gönderme) verilerini seri hale getirmek için çağıran arşivine eklemeden `CSocketFile` veri yazmak için üye işlevleri `CSocket` nesne. Seri durumdan çıkarılacak (alma) veri arşivden ayıklayın. Bu çağrı arşiv neden `CSocketFile` üye işlevleri, verileri okumak için `CSocket` nesne.  
  
> [!TIP]
>  Kullanarak yanı sıra `CSocketFile` ile yapabildiğiniz gibi burada açıklandığı gibi bir tek başına dosya nesnesi olarak kullanabileceğiniz `CFile`, kendi temel sınıfı. Ayrıca `CSocketFile` arşivi tabanlı MFC serileştirme işlevleri ile. Çünkü `CSocketFile` tüm desteklemiyor `CFile`kullanıcının işlevselliği, bazı varsayılan MFC serileştirmek işlevler ile uyumlu değildir `CSocketFile`. Bu, özellikle true `CEditView` sınıfı. Seri hale getirmek denememelisiniz `CEditView` verilerine bir `CArchive` nesne iliştirilmiş bir `CSocketFile` kullanarak nesne `CEditView::SerializeRaw`; kullanma `CEditView::Serialize` yerine. `SerializeRaw` İşlevi gibi işlevleri sağlamak için dosya nesnesi bekliyor `Seek`, o `CSocketFile` sahip değil.  
  
 Kullanırken `CArchive` ile `CSocketFile` ve `CSocket`, bir durum karşılaşabilirsiniz burada `CSocket::Receive` bir döngüye girer (tarafından `PumpMessages(FD_READ)`) istenen bayt miktarı için bekleniyor. Windows sockets FD_READ bildirim başına yalnızca bir alımı ayarlanırken çağrı izin olmasıdır ancak `CSocketFile` ve `CSocket` FD_READ başına birden çok Al çağrılarının izin verir. Hiçbir veri okumak için bir FD_READ alırsanız, uygulamanın yanıt vermemeye başlıyor. Hiçbir zaman başka bir FD_READ alırsanız, yuva iletişim kuran uygulamayı durdurur.  
  
 Aşağıdaki şekilde bu sorunu çözebilirsiniz. İçinde `OnReceive` yuva sınıfınızın çağrı yöntemi `CAsyncSocket::IOCtl(FIONREAD, ...)` çağırmadan önce `Serialize` beklenen veri yuvadan okumak için bir TCP paket (en fazla iletim birimi ağ ortamının boyutunu aştığında, ileti sınıfının yöntemi genellikle en az 1096 bayt). Kullanılabilir veri boyutu gereken daha az ise, alınması ve yalnızca okuma işlemini başlatmak tüm veriler için bekleyin.  
  
 Aşağıdaki örnekte, `m_dwExpected` yaklaşık kullanıcı almak için bekliyor bayt sayısıdır. Başka bir yerde kodunuzda bildirirken, varsayılır.  
  
 [!code-cpp[NVC_MFCSocketThread#4](../../mfc/reference/codesnippet/cpp/csocketfile-class_1.cpp)]  
  
 Daha fazla bilgi için [MFC'de Windows Yuvaları](../../mfc/windows-sockets-in-mfc.md), [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md), yanı [Windows Sockets 2 API](/windows/desktop/WinSock/windows-sockets-start-page-2).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `CSocketFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxsock.h  
  
##  <a name="csocketfile"></a>  CSocketFile::CSocketFile  
 Oluşturur bir `CSocketFile` nesne.  
  
```  
explicit CSocketFile(
    CSocket* pSocket,  
    BOOL bArchiveCompatible = TRUE);
```  
  
### <a name="parameters"></a>Parametreler  
 *pSocket*  
 Eklemek için yuva `CSocketFile` nesne.  
  
 *bArchiveCompatible*  
 Dosya nesnesi ile kullanım için uygun olup olmadığını belirtir bir `CArchive` nesne. Geçişi kullanmak isterseniz FALSE `CSocketFile` tek başına gibi tek başına bir şekilde nesne `CFile` belirli sınırlamalarla birlikte bir nesne. Bu bayrak değişiklikleri nasıl `CArchive` nesne iliştirilmiş `CSocketFile` nesne okumak için arabellek yönetir.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne kapsam dışına gider veya silinen nesnenin yok Edicisi kendisini yuva nesneden ayırır.  
  
> [!NOTE]
>  A `CSocketFile` (sınırlı) dosyası olarak kullanılabilir bir `CArchive` nesne. Varsayılan olarak, `CSocketFile` oluşturucunun *bArchiveCompatible* parametredir TRUE. Bu dosya nesnesini bir arşiv ile kullanılmak üzere olduğunu belirtir. Bir arşiv olmadan dosya nesnesini kullanmak için FALSE geçirin *bArchiveCompatible* parametresi.  
  
 "Arşiv uyumlu" modunda bir `CSocketFile` nesne "kilitlenme." tehlikesi azaltır ve daha iyi performans sağlar Gönderme ve alma yuvalarına birbirine ya da ortak bir kaynak için bekleyen bir kilitlenme oluşur. Bu durum meydana gelebilir `CArchive` nesne çalıştığınız `CSocketFile` , sahip olduğu gibi bir `CFile` nesne. İle `CFile`, Arşiv, istenenden daha az bayt alırsa, dosya sonuna ulaşıldı varsayabilirsiniz.  
  
 İle `CSocketFile`ancak, veri tabanlı ileti; arabellek birden fazla ileti içerebilir, bu nedenle, istenen bayt sayısından daha az alan değil yaptığından dosya sonu. Uygulama ile olabileceği gibi bu durumda engellemez `CFile`, arabellek boş olana kadar iletilerini arabellekteki okuma devam edebilir. [CArchive::IsBufferEmpty](../../mfc/reference/carchive-class.md#isbufferempty) işlevi arşivin arabellek böyle bir durumda durumunu izlemek için yararlıdır.  
  
 Kullanımı hakkında daha fazla bilgi için `CSocketFile`, makalelere göz atın [Windows Yuvaları: yuvaların arşivlerle kullanma](../../mfc/windows-sockets-using-sockets-with-archives.md) ve [Windows Yuvaları: örnek, yuva kullanarak arşivleri](../../mfc/windows-sockets-example-of-sockets-using-archives.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAsyncSocket sınıfı](../../mfc/reference/casyncsocket-class.md)   
 [CSocket Sınıfı](../../mfc/reference/csocket-class.md)
