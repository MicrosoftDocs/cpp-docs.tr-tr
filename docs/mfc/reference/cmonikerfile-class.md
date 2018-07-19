---
title: CMonikerFile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
dev_langs:
- C++
helpviewer_keywords:
- CMonikerFile [MFC], CMonikerFile
- CMonikerFile [MFC], Close
- CMonikerFile [MFC], Detach
- CMonikerFile [MFC], GetMoniker
- CMonikerFile [MFC], Open
- CMonikerFile [MFC], CreateBindContext
ms.assetid: 87be5966-f4f7-4235-bce2-1fa39e9417de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 296e288f017373563b867b02ad26f25ec6bc6227
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/05/2018
ms.locfileid: "37853653"
---
# <a name="cmonikerfile-class"></a>CMonikerFile sınıfı
Veri akışını temsil eder ( [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034)) tarafından adlandırılan bir [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CMonikerFile : public COleStreamFile  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMonikerFile::CMonikerFile](#cmonikerfile)|Oluşturur bir `CMonikerFile` nesne.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMonikerFile::Close](#close)|Ayırır ve akış serbest bırakır ve ad serbest bırakır.|  
|[CMonikerFile::Detach](#detach)|Ayırır `IMoniker` bu `CMonikerFile` nesne.|  
|[CMonikerFile::GetMoniker](#getmoniker)|Geçerli bilinen adını döndürür.|  
|[CMonikerFile::Open](#open)|Bir akışa almak için belirtilen dosyayı açar.|  
  
### <a name="protected-methods"></a>Korumalı Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CMonikerFile::CreateBindContext](#createbindcontext)|Bağlama bağlamı alır veya bir varsayılan bağlama bağlamı oluşturur.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bir bilinen ad, bir dosya için bir yol adı gibi bilgileri içerir. Bir bilinen ad nesne işaretçisi varsa `IMoniker` arabirimi dosyasının gerçekten bulunduğu hakkında diğer belirli bilgilere gerek kalmadan tanımlanan dosyaya erişim alabilirsiniz.  
  
 Türetilmiş `COleStreamFile`, `CMonikerFile` bilinen adı veya bir bilinen adına olun dize gösterimini alır ve takma ad olan akışa bağlar. Ardından, okuma ve akışına yazma. Asıl amacı olan `CMonikerFile` için basit erişim sağlamaktır `IStream`s adlı tarafından `IMoniker`s kendiniz bir akışa bağlamak zorunda değilsiniz böylece henüz `CFile` akışına işlevselliği.  
  
 `CMonikerFile` bir akış dışında bağlamak için kullanılamaz. Depolama veya nesneyi bağlamak istiyorsanız, kullanmalısınız `IMoniker` doğrudan arabirim.  
  
 Akışları ve adlar hakkında daha fazla bilgi için bkz. [COleStreamFile](../../mfc/reference/colestreamfile-class.md) içinde *MFC başvurusu* ve [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) ve [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) içinde Windows SDK'sı.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CFile](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 `CMonikerFile`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxole.h  
  
##  <a name="close"></a>  CMonikerFile::Close  
 Ayırma ve serbest akışa ve ad serbest bırakmak için bu işlevi çağırın.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Açılmamış veya zaten kapalı akışların çağrılabilir.  
  
##  <a name="cmonikerfile"></a>  CMonikerFile::CMonikerFile  
 Oluşturur bir `CMonikerFile` nesne.  
  
```  
CMonikerFile();
```  
  
##  <a name="createbindcontext"></a>  CMonikerFile::CreateBindContext  
 Varsayılan bağlama bağlamı oluşturmak için bu işlevi çağırın.  
  
```  
IBindCtx* CreateBindContext(CFileException* pError);
```  
  
### <a name="parameters"></a>Parametreler  
 *pError*  
 Dosya özel durum işaretçisi. Bir hata olması durumunda, neden ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bağlama bağlamı için bir işaretçi [ıbindctx i](http://msdn.microsoft.com/library/windows/desktop/ms693755) başarılı; Aksi takdirde NULL ile bağlamak için. Örneği ile açıldıysa bir `IBindHost` arabirimi, bağlama bağlamı alınır `IBindHost`. Yoksa hiçbir `IBindHost` arabirimi veya arabirim başarısız bir bağlama bağlamı geri dönmek, bağlama bağlamı oluşturulur. Bir açıklaması için [IBindHost](http://msdn.microsoft.com/library/ie/ms775076) arabirimi, Windows SDK'sı bakın.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir bağlama bağlamı belirli ad bağlama işlemiyle ilgili bilgileri depolayan bir nesnedir. Özel bağlama bağlam sağlamak için bu işlevi geçersiz kılabilirsiniz.  
  
##  <a name="detach"></a>  CMonikerFile::Detach  
 Akış kapatmak için bu işlevi çağırın.  
  
```  
BOOL Detach(CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *pError*  
 Dosya özel durum işaretçisi. Bir hata olması durumunda, neden ayarlanır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
##  <a name="getmoniker"></a>  CMonikerFile::GetMoniker  
 Bir işaretçi geçerli bilinen adını almak için bu işlevi çağırın.  
  
```  
IMoniker* GetMoniker() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli ad arabirim işaretçisi ( [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705)).  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yana `CMonikerFile` bir arabirim değil döndürülen işaretçi başvuru sayısını artırmaz (aracılığıyla [AddRef](http://msdn.microsoft.com/library/windows/desktop/ms691379)), ad yayımlanan ve zaman `CMonikerFile` nesne yayımlanır. Bilinen ad tutun veya kendiniz yayın istiyorsanız gerekir `AddRef` bu.  
  
##  <a name="open"></a>  CMonikerFile::Open  
 Bir dosya veya bilinen ad nesne açmak için bu üye işlevini çağırın.  
  
```  
virtual BOOL Open(
    LPCTSTR lpszURL,  
    CFileException* pError = NULL);

 
virtual BOOL Open(
    IMoniker* pMoniker,  
    CFileException* pError = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 *lpszURL*  
 Bir URL veya açılması için dosyanın dosya adı.  
  
 *pError*  
 Dosya özel durum işaretçisi. Bir hata olması durumunda, neden ayarlanır.  
  
 *pMoniker*  
 Bilinen ad arabirim işaretçisi `IMoniker` akışı elde etmek için kullanılacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa sıfır dışı; Aksi durumda 0.  
  
### <a name="remarks"></a>Açıklamalar  
 *LpszURL* parametresi Macintosh üzerinde kullanılamaz. Yalnızca *pMoniker* biçiminin `Open` Macintosh üzerinde kullanılabilir.  
  
 Bir URL veya dosya adı için kullanabileceğiniz *lpszURL* parametresi. Örneğin:  
  
 [!code-cpp[NVC_MFCWinInet#6](../../mfc/codesnippet/cpp/cmonikerfile-class_1.cpp)]  
  
 - veya -  
  
 [!code-cpp[NVC_MFCWinInet#7](../../mfc/codesnippet/cpp/cmonikerfile-class_2.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [COleStreamFile sınıfı](../../mfc/reference/colestreamfile-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CAsyncMonikerFile Sınıfı](../../mfc/reference/casyncmonikerfile-class.md)
