---
title: "CMonikerFile sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMonikerFile
- AFXOLE/CMonikerFile
- AFXOLE/CMonikerFile::CMonikerFile
- AFXOLE/CMonikerFile::Close
- AFXOLE/CMonikerFile::Detach
- AFXOLE/CMonikerFile::GetMoniker
- AFXOLE/CMonikerFile::Open
- AFXOLE/CMonikerFile::CreateBindContext
dev_langs: C++
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3dfdf86a4375521d7db084b60c549b08a54dc992
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cmonikerfile-class"></a>CMonikerFile sınıfı
Veri akışı temsil eder ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) tarafından adlı bir [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Oluşturan bir `CMonikerFile` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Ayırır ve akış serbest bırakır ve bilinen ad serbest bırakır.|  
|[CMonikerFile::Detach](#detach)|Ayırır `IMoniker` bu `CMonikerFile` nesnesi.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Geçerli ad döndürür.|  
|[CMonikerFile::Open](#open)|Bir akış almak için belirtilen dosyayı açar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Bağlama bağlamı alır veya başlatılmış varsayılan bağlama bağlamı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bilinen ad kadar bir dosya için bir yol adı gibi bilgileri içerir. Bir bilinen ad nesne için bir işaretçi varsa `IMoniker` arabirimi, dosyanın gerçekten bulunduğu hakkında diğer belirli bilgiler olmadan tanımlanan dosyaya erişim alabilirsiniz.  
  
 Türetilmiş `COleStreamFile`, `CMonikerFile` bir ad veya bir bilinen ad yapın dize gösterimini alır ve özniteliğinde bir ad olduğu akış bağlar. Ardından, okuma ve o akışına yazma. Gerçek amacı `CMonikerFile` basit erişim sağlamak için `IStream`s adlı `IMoniker`s böylece bir akışa kendiniz bağlamak zorunda değilsiniz henüz `CFile` akışa işlevselliği.  
  
 `CMonikerFile`bir akış dışında her şey bağlamak için kullanılamaz. Depolama veya nesneyi bağlamak istiyorsanız, kullanmalısınız `IMoniker` doğrudan arabirim.  
  
 Akışlar ve adları hakkında daha fazla bilgi için bkz: [COleStreamFile](../../mfc/reference/colestreamfile-class.md) içinde *MFC başvurusu* ve [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) ve [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) içinde Windows SDK.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="close"></a>CMonikerFile::Close  
 Ayırma ve akış serbest bırakın ve bilinen ad serbest bırakmak için bu işlevini çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Açılmamış ya da zaten kapalı akışların çağrılabilir.  
  
##  <a name="cmonikerfile"></a>CMonikerFile::CMonikerFile  
 Oluşturan bir `CMonikerFile` nesnesi.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>CMonikerFile::CreateBindContext  
 Başlatılan varsayılan bağlama bağlamı oluşturmak için bu işlevini çağırın.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Parametreler  
 `pError`  
 Dosya özel durumu için bir işaretçi. Bir hata durumunda neden ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlama bağlamı için bir işaretçi [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) başarılı; Aksi takdirde ile bağlamak için **NULL**. Örnek ile açılmışsa bir `IBindHost` arabirimi, bağlama bağlamı alınır `IBindHost`. Varsa hiçbir `IBindHost` arabirimi veya arabirimi başarısız olursa bir bağlama bağlamı geri dönmek, bağlama bağlamı oluşturulur. Bir açıklaması için [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) arabirimi, Windows SDK konusuna bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bağlama bağlamı belirli ad bağlama işlemi hakkında bilgi depolayan bir nesnedir. Özel bağlama bağlamı sağlamak için bu işlevi geçersiz kılabilirsiniz.  
  
##  <a name="detach"></a>CMonikerFile::Detach  
 Akış kapatmak için bu işlevini çağırın.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `pError`  
 Dosya özel durumu için bir işaretçi. Bir hata durumunda neden ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="getmoniker"></a>CMonikerFile::GetMoniker  
 Geçerli ad için bir işaretçi almak için bu işlevini çağırın.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ad arabirimi işaretçisi ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yana `CMonikerFile` bir arabirim değil döndürülen işaretçi başvuru sayımı artırmaz (aracılığıyla [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), ve bilinen ad serbest zaman `CMonikerFile` nesne yayımlanır. Bilinen ad tutun veya kendiniz serbest istiyorsanız, şunları yapmalısınız `AddRef` onu.  
  
##  <a name="open"></a>CMonikerFile::Open  
 Bir dosya ya da ad nesnesini açmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `lpszURL`  
 Bir URL veya açılması için dosyanın.  
  
 `pError`  
 Dosya özel durumu için bir işaretçi. Bir hata durumunda neden ayarlanır.  
  
 `pMoniker`  
 Ad arayüzü için bir işaretçi `IMoniker` bir akış almak için kullanılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 `lpszURL` Parametresi Macintosh üzerinde kullanılamaz. Yalnızca `pMoniker` biçiminde **açık** Macintosh üzerinde kullanılabilir.  
  
 Bir URL veya bir dosya adı için kullanabileceğiniz `lpszURL` parametresi. Örneğin:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - veya -  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleStreamFile sınıfı](../../mfc/reference/colestreamfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
