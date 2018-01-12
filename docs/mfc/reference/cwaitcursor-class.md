---
title: "CWaitCursor sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CWaitCursor
- AFXWIN/CWaitCursor
- AFXWIN/CWaitCursor::CWaitCursor
- AFXWIN/CWaitCursor::Restore
dev_langs: C++
helpviewer_keywords:
- CWaitCursor [MFC], CWaitCursor
- CWaitCursor [MFC], Restore
ms.assetid: 5dfae2ff-d7b6-4383-b0ad-91e0868c67b3
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1cf5c850158e445e7695b85e540b1e0c162e621c
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/03/2018
---
# <a name="cwaitcursor-class"></a>CWaitCursor sınıfı
Uzun bir işlem yaparken, genellikle bir kum saati görüntülenen bir bekleme imleç göstermek için bir satır içi bir yol sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CWaitCursor  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWaitCursor::CWaitCursor](#cwaitcursor)|Oluşturan bir `CWaitCursor` nesne ve bekleme imleci görüntüler.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CWaitCursor::Restore](#restore)|Değiştirilmiş sonra bekleme imleci geri yükler.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CWaitCursor`bir taban sınıfı yok.  
  
 İyi Windows uygulamalarını programlama belirgin bir süre alan bir işlem gerçekleştiriyorsunuz bulunduğunda bir bekleme imleç görüntülenmesini gerektirir.  
  
 Bekleme imleç görüntülemek için yalnızca tanımlayabilir bir `CWaitCursor` uzun işlemi gerçekleştirir kodundan önce değişken. Nesnenin oluşturucusu otomatik olarak görüntülenecek bekleme imleci neden olur.  
  
 Nesne kapsam dışında gittiğinde (bloğunda sonunda `CWaitCursor` nesne bildirilen), kendi yıkıcı imleci önceki imleci ayarlar. Diğer bir deyişle, nesne gerekli temizlemenin otomatik olarak gerçekleştirir.  
  
> [!NOTE]
>  Kendi oluşturucular ve Yıkıcılar nasıl çalıştığını, nedeniyle `CWaitCursor` nesneler her zaman yerel değişkenleri olarak bildirilen — genel değişkenleri olarak hiçbir zaman bildirilen veya ile ayrılmış **yeni**.  
  
 İmleci görüntüleme gibi bir ileti kutusu veya iletişim kutusu, çağrı değiştirilecek neden bir işlem gerçekleştiriyorsanız, [geri](#restore) bekleme imleci geri yüklemek için üye işlevi. Çağırmak uygundur **geri** bile ne zaman bir bekleme İmleç şu anda görüntülenir.  
  
 Bekleme imleç görüntülemek için başka bir yolu birleşimi kullanmaktır [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor), [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)ve belki de [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor). Ancak, `CWaitCursor` uzun işlemi bittiğinde imleci önceki imleci ayarlamanız gerekmez çünkü kullanmak daha kolay olur.  
  
> [!NOTE]
>  MFC ayarlar ve imleci kullanarak geri yükler [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor) sanal işlev. Özel davranışı sağlamak için bu işlevi geçersiz kılabilirsiniz.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `CWaitCursor`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxwin.h  
  
## <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#62](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_1.cpp)]  
  
##  <a name="cwaitcursor"></a>CWaitCursor::CWaitCursor  
 Bekleme imleç görüntülemek için yalnızca bildirme bir `CWaitCursor` uzun işlemi gerçekleştirir kodundan önce nesnesi.  
  
```  
CWaitCursor();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturucu otomatik olarak görüntülenecek bekleme imleci neden olur.  
  
 Nesne kapsam dışında gittiğinde (bloğunda sonunda `CWaitCursor` nesne bildirilen), kendi yıkıcı imleci önceki imleci ayarlar. Diğer bir deyişle, nesne gerekli temizlemenin otomatik olarak gerçekleştirir.  
  
 Yıkıcı (olabilen işlevi bitişinden önce) bloğun sonunda bekleme imleci yalnızca işlevinizde bir parçası etkin hale getirmek için çağrıldığından emin olayının avantajından yararlanabilirsiniz. Bu teknik aşağıdaki ikinci örnekte gösterilir.  
  
> [!NOTE]
>  Kendi oluşturucular ve Yıkıcılar nasıl çalıştığını, nedeniyle `CWaitCursor` nesneler her zaman yerel değişkenleri olarak bildirilen — genel değişkenleri olarak hiçbir zaman bildirilen veya ile ayrılmış **yeni**.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#63](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_2.cpp)]  
  
##  <a name="restore"></a>CWaitCursor::Restore  
 Bekleme imleci geri yüklemek için bir ileti veya bekleme imleci için başka bir imleç değişebilir iletişim kutusu görüntüleme gibi bir işlem gerçekleştirildikten sonra bu işlevini çağırın.  
  
```  
void Restore();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Arama için Tamam'ı olan **geri** bile bekleme imleci şu anda görüntülendiğinde.  
  
 Bekleme imleci hangi birinde dışında bir işlevdeki sırada geri yüklemeniz gerekiyorsa `CWaitCursor` nesne bildirilen, çağırabilirsiniz [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCWindowing#64](../../mfc/reference/codesnippet/cpp/cwaitcursor-class_3.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CCmdTarget::BeginWaitCursor](../../mfc/reference/ccmdtarget-class.md#beginwaitcursor)   
 [CCmdTarget::EndWaitCursor](../../mfc/reference/ccmdtarget-class.md#endwaitcursor)   
 [CCmdTarget::RestoreWaitCursor](../../mfc/reference/ccmdtarget-class.md#restorewaitcursor)   
 [CWinApp::DoWaitCursor](../../mfc/reference/cwinapp-class.md#dowaitcursor)   
 [I: fare imleci bir Microsoft Foundation Class uygulamada nasıl değişiyor](http://go.microsoft.com/fwlink/p/?linkid=128044)



