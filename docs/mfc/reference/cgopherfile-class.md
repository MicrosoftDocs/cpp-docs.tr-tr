---
title: CGopherFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CGopherFile
- AFXINET/CGopherFile
- AFXINET/CGopherFile::CGopherFile
dev_langs:
- C++
helpviewer_keywords:
- CGopherFile [MFC], CGopherFile
ms.assetid: 3ca9898f-8cdb-4495-bbde-46d40100feda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c6c4f87ffb1538e581320e9d6f36e8d4fbc6fc12
ms.sourcegitcommit: 6408139d5f5ff8928f056bde93d20eecb3520361
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/02/2018
ms.locfileid: "37335688"
---
# <a name="cgopherfile-class"></a>CGopherFile sınıfı
Bulmak ve bir gopher sunucusunda dosyaları okumak için gereken işlevleri sağlar.  
  
> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri bırakılmıştır, Windows XP platformu üzerinde çalışmaz, ancak önceki platformları üzerinde çalışmaya devam eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Oluşturur bir `CGopherFile` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gopher hizmet bu hizmeti bilgileri bulmak için çoğunlukla bir menü yönlendirmeli arabirimi gördüğünden bir gopher dosyaya veri yazmak kullanıcılar izin vermez. `CGopherFile` Üye işlevleri `Write`, `WriteString`, ve `Flush` için uygulanmadı `CGopherFile`. Bu işlevler çağırma bir `CGopherFile` nesnesi döndürür bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Hakkında daha fazla bilgi edinmek için `CGopherFile` diğer Internet MFC sınıfları ile çalışır, başlıklı makaleye bakın [Winınet'in Internet programlama](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [Cınternetfile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile  
 Bu üye işlevi oluşturmak için çağrılan bir `CGopherFile` nesne.  
  
```  
CGopherFile(
    HINTERNET hFile,  
    CGopherLocator& refLocator,  
    CGopherConnection* pConnection);

 
CGopherFile(
    HINTERNET hFile,  
    HINTERNET hSession,  
    LPCTSTR pstrLocator,  
    DWORD dwLocLen,  
    DWORD_PTR dwContext);
```  
  
### <a name="parameters"></a>Parametreler  
 *Hfıle*  
 HINTERNET dosyaya tanıtıcı.  
  
 *refLocator*  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesne.  
  
 *pConnection*  
 Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesne.  
  
 *hSession*  
 Geçerli Internet oturumu için bir tanıtıcı.  
  
 *pstrLocator*  
 Gopher sunucusu bulmak için kullanılan bir dizeye bir işaretçi. Bkz: [Gopher oturumları](cgopherlocator-class.md) gopher bulucuları hakkında daha fazla bilgi.  
  
 *dwLocLen*  
 Bayt sayısını içeren bir DWORD *pstrLocator*.  
  
 *dwContext*  
 Açılan dosyanın içerik tanımlayıcısı için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Gereksinim duyduğunuz bir `CGopherFile` bir gopher Internet oturumu sırasında bir dosyadan okunan nesne.  
  
 Asla oluşturma bir `CGopherFile` doğrudan nesne. Bunun yerine çağrı [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) bir gopher sunucusunda bir dosyayı açmak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Cınternetfile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [Cınternetfile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator sınıfı](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
