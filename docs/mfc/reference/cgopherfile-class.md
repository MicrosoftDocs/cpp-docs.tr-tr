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
ms.openlocfilehash: 98fa4b2a489b8abb3951719dc74e618a054a4025
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366889"
---
# <a name="cgopherfile-class"></a>CGopherFile sınıfı
Bulma ve bir gopher sunucusundaki dosyaları okumak için işlevsellik sağlar.  
  
> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri Windows XP platformunda çalışmaz, ancak daha önceki platformlar üzerinde çalışmaya devam edecek kullanım dışı bırakıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGopherFile : public CInternetFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherFile::CGopherFile](#cgopherfile)|Oluşturan bir `CGopherFile` nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 Gopher hizmeti, kullanıcıların bu hizmet bilgileri bulmak için çoğunlukla bir menü yönlendirmeli arabirimi gördüğünden veri bir gopher dosyaya yazmak izin vermez. `CGopherFile` Üye işlevleri **yazma**, `WriteString`, ve `Flush` için uygulanmadı `CGopherFile`. Bu işlevler çağrılması bir `CGopherFile` nesnesi döndürür bir [CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).  
  
 Hakkında daha fazla bilgi için `CGopherFile` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [CStdioFile](../../mfc/reference/cstdiofile-class.md)  
  
 [CInternetFile](../../mfc/reference/cinternetfile-class.md)  
  
 `CGopherFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cgopherfile"></a>  CGopherFile::CGopherFile  
 Bu üye işlevi oluşturmak için çağrılan bir `CGopherFile` nesnesi.  
  
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
 `hFile`  
 İçin bir tanıtıcı bir `HINTERNET` dosyası.  
  
 `refLocator`  
 Bir başvuru bir [CGopherLocator](../../mfc/reference/cgopherlocator-class.md) nesnesi.  
  
 `pConnection`  
 Bir işaretçi bir [CGopherConnection](../../mfc/reference/cgopherconnection-class.md) nesnesi.  
  
 `hSession`  
 Geçerli Internet oturumu için bir tanıtıcı.  
  
 `pstrLocator`  
 Gopher sunucusunu bulmak için kullanılan bir dize için bir işaretçi. Bkz: [Gopher oturumları](cgopherlocator-class.md) gopher bulucular hakkında daha fazla bilgi.  
  
 *dwLocLen*  
 Bayt sayısını içeren bir DWORD `pstrLocator`.  
  
 `dwContext`  
 Açılmakta dosya Bağlam tanıtıcısı gösteren bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Gereksinim duyduğunuz bir `CGopherFile` bir gopher Internet oturumu sırasında bir dosyadan okunan nesne.  
  
 Hiçbir zaman oluşturduğunuz bir `CGopherFile` doğrudan nesne. Bunun yerine, çağrı [CGopherConnection::OpenFile](../../mfc/reference/cgopherconnection-class.md#openfile) bir gopher sunucusunda bir dosyayı açmaya.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CInternetFile sınıfı](../../mfc/reference/cinternetfile-class.md)   
 [CGopherLocator sınıfı](../../mfc/reference/cgopherlocator-class.md)   
 [CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)   
 [CGopherConnection Sınıfı](../../mfc/reference/cgopherconnection-class.md)
