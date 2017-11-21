---
title: "COleStreamFile sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleStreamFile
- AFXOLE/COleStreamFile
- AFXOLE/COleStreamFile::COleStreamFile
- AFXOLE/COleStreamFile::Attach
- AFXOLE/COleStreamFile::CreateMemoryStream
- AFXOLE/COleStreamFile::CreateStream
- AFXOLE/COleStreamFile::Detach
- AFXOLE/COleStreamFile::GetStream
- AFXOLE/COleStreamFile::OpenStream
dev_langs: C++
helpviewer_keywords:
- COleStreamFile [MFC], COleStreamFile
- COleStreamFile [MFC], Attach
- COleStreamFile [MFC], CreateMemoryStream
- COleStreamFile [MFC], CreateStream
- COleStreamFile [MFC], Detach
- COleStreamFile [MFC], GetStream
- COleStreamFile [MFC], OpenStream
ms.assetid: e4f93698-e17c-4a18-a7c0-4b4df8eb4d93
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 1c7b9e26013a505f5de137797964ed19376569a2
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="colestreamfile-class"></a>COleStreamFile sınıfı
Veri akışı temsil eder ( `IStream`) bileşik bir dosyada OLE yapılı depolama bir parçası olarak.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleStreamFile : public CFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleStreamFile::COleStreamFile](#colestreamfile)|Oluşturan bir `COleStreamFile` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleStreamFile::Attach](#attach)|Bir akış nesnesi ile ilişkilendirir.|  
|[COleStreamFile::CreateMemoryStream](#creatememorystream)|Genel bellekten bir akış oluşturur ve nesnesi ile ilişkilendirir.|  
|[COleStreamFile::CreateStream](#createstream)|Bir akış oluşturur ve nesnesi ile ilişkilendirir.|  
|[COleStreamFile::Detach](#detach)|Nesne akıştan keser.|  
|[COleStreamFile::GetStream](#getstream)|Geçerli akışa döndürür.|  
|[COleStreamFile::OpenStream](#openstream)|Güvenli bir şekilde bir akış açar ve nesnesi ile ilişkilendirir.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir `IStorage` nesne akışı açılamıyor veya bir bellek akış olmadığı sürece oluşturulan önce bulunmalıdır.  
  
 `COleStreamFile`nesneleri yönetilen tam olarak gibi [CFile](../../mfc/reference/cfile-class.md) nesneleri.  
  
 Akışlar ve depolamayı düzenleme hakkında daha fazla bilgi için bkz: [kapsayıcılar: bileşik dosyaları](../../mfc/containers-compound-files.md)...  
  
 Daha fazla bilgi için bkz: [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) ve [IStorage](http://msdn.microsoft.com/library/windows/desktop/aa380015) Windows SDK'sındaki.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 `COleStreamFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="attach"></a>COleStreamFile::Attach  
 Sağlanan OLE akış ile ilişkilendirir `COleStreamFile` nesnesi.  
  
```  
void Attach(LPSTREAM lpStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpStream`  
 OLE akışa işaret ( `IStream`) nesne ile ilişkili olmalıdır. Olamaz **NULL**.  
  
### <a name="remarks"></a>Açıklamalar  
 Nesne zaten bir OLE akış ile ilişkilendirilmemiş olması gerekir.  
  
 Daha fazla bilgi için bkz: [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows SDK'sındaki.  
  
##  <a name="colestreamfile"></a>COleStreamFile::COleStreamFile  
 Oluşturur bir `COleStreamFile` nesnesi.  
  
```  
COleStreamFile(LPSTREAM lpStream = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpStream`  
 İşaretçi OLE akışa nesne ile ilişkili olabilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `lpStream` olan **NULL**nesne OLE akış ile ilişkili değil, aksi takdirde, nesne sağlanan OLE akış ile ilişkilidir.  
  
 Daha fazla bilgi için bkz: [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows SDK'sındaki.  
  
##  <a name="creatememorystream"></a>COleStreamFile::CreateMemoryStream  
 Güvenli bir şekilde hata normal, beklenen bir durum olduğu yeni bir akış genel, paylaşılan bellek yetersiz oluşturur.  
  
```  
BOOL CreateMemoryStream(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pError`  
 İşaret eden bir [CFileException](../../mfc/reference/cfileexception-class.md) nesne veya **NULL** oluşturma işleminin tamamlanma durumunu gösterir. Akış oluşturulmaya çalışılırken tarafından oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlayın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Bellek OLE alt sistemi tarafından ayrılır.  
  
 Daha fazla bilgi için bkz: [CreateStreamOnHGlobal](http://msdn.microsoft.com/library/windows/desktop/aa378980) Windows SDK'sındaki.  
  
##  <a name="createstream"></a>COleStreamFile::CreateStream  
 Güvenli bir şekilde yeni bir akış burada bir hata çok normal, beklenen bir durumdur sağlanan depolama nesnesinde oluşturur.  
  
```  
BOOL CreateStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive|modeCreate,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpStorage`  
 Oluşturulacak akış içeren OLE depolama nesne noktalarına. Olamaz **NULL**.  
  
 `lpszStreamName`  
 Oluşturulacak Akış adı. Olamaz **NULL**.  
  
 `nOpenFlags`  
 Akış açarken kullanılacak erişim modu. Özel, okuma/yazma ve oluşturma modları varsayılan olarak kullanılır. Kullanılabilir modları tam bir listesi için bkz: [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 İşaret eden bir [CFileException](../../mfc/reference/cfileexception-class.md) nesne veya **NULL**. Akış oluşturulmaya çalışılırken tarafından oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlayın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış başarıyla oluşturulduysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Açık başarısız olursa dosya özel durum oluşturulur ve `pError` değil **NULL**.  
  
 Daha fazla bilgi için bkz: [IStorage::CreateStream](http://msdn.microsoft.com/library/windows/desktop/aa380020) Windows SDK'sındaki.  
  
##  <a name="detach"></a>COleStreamFile::Detach  
 Nesne akıştan akış kapatmadan keser.  
  
```  
LPSTREAM Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış işaretçisine ( `IStream`), nesne ile ilişkili.  
  
### <a name="remarks"></a>Açıklamalar  
 Program bitirmeden akış diğer bazı biçimde kapatılması gerekir.  
  
 Daha fazla bilgi için bkz: [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) Windows SDK'sındaki.  
  
##  <a name="getstream"></a>COleStreamFile::GetStream  
 Bir işaretçi geçerli akışına döndürmek için bu işlevini çağırın.  
  
```  
IStream* GetStream() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli akış arabirimi işaretçisi ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)).  
  
##  <a name="openstream"></a>COleStreamFile::OpenStream  
 Var olan bir akış açar.  
  
```  
BOOL OpenStream(
    LPSTORAGE lpStorage,  
    LPCTSTR lpszStreamName,  
    DWORD nOpenFlags = modeReadWrite|shareExclusive,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpStorage`  
 Açılacak akışın içeren OLE depolama nesne noktalarına. Olamaz **NULL**.  
  
 `lpszStreamName`  
 Açılacak akışın adı. Olamaz **NULL**.  
  
 `nOpenFlags`  
 Akış açarken kullanılacak erişim modu. Özel ve okuma/yazma modları, varsayılan olarak kullanılır. Kullanılabilir modları tam listesi için bkz: [CFile::CFile](../../mfc/reference/cfile-class.md#cfile).  
  
 `pError`  
 İşaret eden bir [CFileException](../../mfc/reference/cfileexception-class.md) nesne veya **NULL**. Akış açmaya tarafından oluşturulan olası özel durumları izlemek istiyorsanız bu parametreyi sağlayın.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Akış başarıyla açılırsa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Açık başarısız olursa dosya özel durum oluşturulur ve `pError` değil **NULL**.  
  
 Daha fazla bilgi için bkz: [IStorage::OpenStream](http://msdn.microsoft.com/library/windows/desktop/aa380025) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CFile sınıfı](../../mfc/reference/cfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)



