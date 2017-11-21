---
title: "CGopherLocator sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CGopherLocator
- AFXINET/CGopherLocator
- AFXINET/CGopherLocator::CGopherLocator
- AFXINET/CGopherLocator::GetLocatorType
dev_langs: C++
helpviewer_keywords:
- CGopherLocator [MFC], CGopherLocator
- CGopherLocator [MFC], GetLocatorType
ms.assetid: 6fcc015f-5ae6-4959-b936-858634c71019
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 477debc5c64924e885a296a88b4d6e047f79b9ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="cgopherlocator-class"></a>CGopherLocator sınıfı
Bir gopher "Bulucusu" bir gopher sunucudan alır, Bulucu'nın türü belirler ve Bulucu için kullanılabilir hale getirir [CGopherFileFind](../../mfc/reference/cgopherfilefind-class.md).  
  
> [!NOTE]
>  Sınıfları `CGopherConnection`, `CGopherFile`, `CGopherFileFind`, `CGopherLocator` ve üyeleri Windows XP platformunda çalışmaz, ancak daha önceki platformlar üzerinde çalışmaya devam edecek kullanım dışı bırakıldı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CGopherLocator : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherLocator::CGopherLocator](#cgopherlocator)|Oluşturan bir `CGopherLocator` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherLocator::GetLocatorType](#getlocatortype)|Gopher Bulucu ayrıştırır ve özniteliklerini belirler.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CGopherLocator::operator LPCTSTR](#operator_lpctstr)|İçinde depolanan karakterlerin doğrudan erişir bir `CGopherLocator` C stili dize olarak nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir uygulama, o sunucudan bilgi alabilmeleri gopher sunucunun Bulucu almanız gerekir. Bulucu olduğunda, onu Konumlandırıcı opak belirteci olarak ele almanız gerekir.  
  
 Her gopher Bulucu dosyası veya sunucu bulundu türünü belirleme özniteliklere sahiptir. Bkz: [GetLocatorType](#getlocatortype) gopher Bulucuyu türleri listesi.  
  
 Uygulama çağrılar için Bulucu normalde kullanan [CGopherFileFind::FindFile](../../mfc/reference/cgopherfilefind-class.md#findfile) belirli bir bilgiyi alınamadı.  
  
 Hakkında daha fazla bilgi için `CGopherLocator` diğer MFC Internet sınıfları ile works başlıklı makaleye bakın [Internet programlama WinINet ile](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CGopherLocator`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxinet.h  
  
##  <a name="cgopherlocator"></a>CGopherLocator::CGopherLocator  
 Bu üye işlevi oluşturmak için çağrılan bir `CGopherLocator` nesnesi.  
  
```  
CGopherLocator(const CGopherLocator& ref);
```  
  
### <a name="parameters"></a>Parametreler  
 `ref`  
 Bir sabit başvuru `CGopherLocator` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir zaman oluşturduğunuz bir `CGopherLocator` doğrudan nesne. Bunun yerine, çağrı [CGopherConnection::CreateLocator](../../mfc/reference/cgopherconnection-class.md#createlocator) oluşturmak ve bir işaretçi döndürmek için `CGopherLocator` nesnesi.  
  
##  <a name="getlocatortype"></a>CGopherLocator::GetLocatorType  
 Bulucu türünü almak için bu üye işlevini çağırın.  
  
```  
BOOL GetLocatorType(DWORD& dwRef) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *dwRef*  
 Bir başvuru bir `DWORD` Bulucu türünü alırsınız. Bkz: **açıklamalar** Bulucu türlerinin bir tablo için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0. Çağrı başarısız olursa, Win32 işlevi [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) hatanın nedenini belirlemek için çağrılabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası türleri aşağıdaki gibidir:  
  
|Değer|Açıklama|  
|-----------|-------------|  
|GOPHER_TYPE_TEXT_FILE|Bir ASCII metin dosyası.|  
|GOPHER_TYPE_DIRECTORY|Bir dizin ek Gopher öğesi.|  
|GOPHER_TYPE_CSO|CSO telefon rehberi sunucu.|  
|GOPHER_TYPE_ERROR|Bir hata koşulu belirtir.|  
|GOPHER_TYPE_MAC_BINHEX|Macintosh dosyası BINHEX biçiminde.|  
|GOPHER_TYPE_DOS_ARCHIVE|Bir DOS arşiv dosyası.|  
|GOPHER_TYPE_UNIX_UUENCODED|Bir UUENCODED dosyası.|  
|GOPHER_TYPE_INDEX_SERVER|Bir dizin sunucusu.|  
|GOPHER_TYPE_TELNET|Telnet sunucusu.|  
|GOPHER_TYPE_BINARY|İkili dosya.|  
|GOPHER_TYPE_REDUNDANT|Yinelenen bir sunucu. İçinde yer alan bilgileri birincil sunucusunun yineleniyor. Birincil sunucu GOPHER_TYPE_REDUNDANT türü olmayan son dizin girişi ' dir.|  
|GOPHER_TYPE_TN3270|TN3270 sunucu.|  
|GOPHER_TYPE_GIF|Bir GIF grafik dosyası.|  
|GOPHER_TYPE_IMAGE|Bir görüntü dosyası.|  
|GOPHER_TYPE_BITMAP|Bir bit eşlem dosyası.|  
|GOPHER_TYPE_MOVIE|Film dosyası.|  
|GOPHER_TYPE_SOUND|Ses dosyası.|  
|GOPHER_TYPE_HTML|Bir HTML belgesi.|  
|GOPHER_TYPE_PDF|Bir PDF dosyası.|  
|GOPHER_TYPE_CALENDAR|Bir takvim dosyası.|  
|GOPHER_TYPE_INLINE|Satır içi dosya.|  
|GOPHER_TYPE_UNKNOWN|Öğe türü bilinmiyor.|  
|GOPHER_TYPE_ASK|Ask + öğe.|  
|GOPHER_TYPE_GOPHER_PLUS|Gopher + öğesi.|  
  
##  <a name="operator_lpctstr"></a>CGopherLocator::operator LPCTSTR  
 Bu yararlı atama işleci içinde yer alan null ile sonlandırılmış C dize erişmek için verimli bir yöntem sağlar bir `CGopherLocator` nesnesi.  
  
```  
operator LPCTSTR () const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizesinin veri için bir karakter işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hiçbir karakter kopyalanır; yalnızca bir işaretçi döndürdü.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CGopherFileFind sınıfı](../../mfc/reference/cgopherfilefind-class.md)
