---
title: "COleSafeArray sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleSafeArray
- AFXDISP/COleSafeArray
- AFXDISP/COleSafeArray::COleSafeArray
- AFXDISP/COleSafeArray::AccessData
- AFXDISP/COleSafeArray::AllocData
- AFXDISP/COleSafeArray::AllocDescriptor
- AFXDISP/COleSafeArray::Attach
- AFXDISP/COleSafeArray::Clear
- AFXDISP/COleSafeArray::Copy
- AFXDISP/COleSafeArray::Create
- AFXDISP/COleSafeArray::CreateOneDim
- AFXDISP/COleSafeArray::Destroy
- AFXDISP/COleSafeArray::DestroyData
- AFXDISP/COleSafeArray::DestroyDescriptor
- AFXDISP/COleSafeArray::Detach
- AFXDISP/COleSafeArray::GetByteArray
- AFXDISP/COleSafeArray::GetDim
- AFXDISP/COleSafeArray::GetElement
- AFXDISP/COleSafeArray::GetElemSize
- AFXDISP/COleSafeArray::GetLBound
- AFXDISP/COleSafeArray::GetOneDimSize
- AFXDISP/COleSafeArray::GetUBound
- AFXDISP/COleSafeArray::Lock
- AFXDISP/COleSafeArray::PtrOfIndex
- AFXDISP/COleSafeArray::PutElement
- AFXDISP/COleSafeArray::Redim
- AFXDISP/COleSafeArray::ResizeOneDim
- AFXDISP/COleSafeArray::UnaccessData
- AFXDISP/COleSafeArray::Unlock
dev_langs:
- C++
helpviewer_keywords:
- COleSafeArray [MFC], COleSafeArray
- COleSafeArray [MFC], AccessData
- COleSafeArray [MFC], AllocData
- COleSafeArray [MFC], AllocDescriptor
- COleSafeArray [MFC], Attach
- COleSafeArray [MFC], Clear
- COleSafeArray [MFC], Copy
- COleSafeArray [MFC], Create
- COleSafeArray [MFC], CreateOneDim
- COleSafeArray [MFC], Destroy
- COleSafeArray [MFC], DestroyData
- COleSafeArray [MFC], DestroyDescriptor
- COleSafeArray [MFC], Detach
- COleSafeArray [MFC], GetByteArray
- COleSafeArray [MFC], GetDim
- COleSafeArray [MFC], GetElement
- COleSafeArray [MFC], GetElemSize
- COleSafeArray [MFC], GetLBound
- COleSafeArray [MFC], GetOneDimSize
- COleSafeArray [MFC], GetUBound
- COleSafeArray [MFC], Lock
- COleSafeArray [MFC], PtrOfIndex
- COleSafeArray [MFC], PutElement
- COleSafeArray [MFC], Redim
- COleSafeArray [MFC], ResizeOneDim
- COleSafeArray [MFC], UnaccessData
- COleSafeArray [MFC], Unlock
ms.assetid: f45a5224-5f48-40ec-9ddd-287ef9740150
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 39c7a471b5c397c430f419514b9ebf1d4da62f62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="colesafearray-class"></a>COleSafeArray sınıfı
Rastgele tür ve boyut dizilerle çalışmaya yönelik bir sınıf.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class COleSafeArray : public tagVARIANT  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleSafeArray::COleSafeArray](#colesafearray)|Oluşturan bir `COleSafeArray` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleSafeArray::AccessData](#accessdata)|Dizi veri için bir işaretçi alır.|  
|[COleSafeArray::AllocData](#allocdata)|Dizi için bellek ayırır.|  
|[COleSafeArray::AllocDescriptor](#allocdescriptor)|Bellek için güvenli diziye tanımlayıcısı ayırır.|  
|[COleSafeArray::Attach](#attach)|Var olan denetim verir **değişken** için dizi `COleSafeArray` nesnesi.|  
|[COleSafeArray::Clear](#clear)|Arka plandaki tüm verileri boşaltır **değişken**.|  
|[COleSafeArray::Copy](#copy)|Var olan bir dizi bir kopyasını oluşturur.|  
|[COleSafeArray::Create](#create)|Güvenli bir dizi oluşturur.|  
|[COleSafeArray::CreateOneDim](#createonedim)|Bir tek boyutlu oluşturur `COleSafeArray` nesnesi.|  
|[COleSafeArray::Destroy](#destroy)|Var olan bir dizi bozar.|  
|[COleSafeArray::DestroyData](#destroydata)|Güvenli bir dizi verilerde yok eder.|  
|[COleSafeArray::DestroyDescriptor](#destroydescriptor)|Güvenli bir dizi tanımlayıcısının bozar.|  
|[COleSafeArray::Detach](#detach)|Ayırır **değişken** gelen dizi `COleSafeArray` (verileri değil boşaltılması böylece) nesne.|  
|[COleSafeArray::GetByteArray](#getbytearray)|Güvenli diziye içeriğini kopyalar bir [CLongBinary](../../mfc/reference/cbytearray-class.md).|  
|[COleSafeArray::GetDim](#getdim)|Dizideki boyut sayısını döndürür.|  
|[COleSafeArray::GetElement](#getelement)|Güvenli dizinin tek bir öğesi alır.|  
|[COleSafeArray::GetElemSize](#getelemsize)|Güvenli bir dizide bir öğe bayt cinsinden boyutu döndürür.|  
|[COleSafeArray::GetLBound](#getlbound)|Herhangi bir güvenli bir dizi boyutu alt sınırı döndürür.|  
|[COleSafeArray::GetOneDimSize](#getonedimsize)|Tek boyutlu içinde öğe sayısını döndürür `COleSafeArray` nesnesi.|  
|[COleSafeArray::GetUBound](#getubound)|Herhangi bir güvenli bir dizi boyutu üst sınırı döndürür.|  
|[COleSafeArray::Lock](#lock)|Bir dizinin kilit sayısını artırır ve dizi veri için bir işaretçi dizi tanımlayıcısındaki yerleştirir.|  
|[COleSafeArray::PtrOfIndex](#ptrofindex)|Bir işaretçi dizinli öğesi döndürür.|  
|[COleSafeArray::PutElement](#putelement)|Tek bir öğe diziye atar.|  
|[COleSafeArray::Redim](#redim)|Güvenli bir dizi en az önemli (sağdaki) bağlı olarak değiştirir.|  
|[COleSafeArray::ResizeOneDim](#resizeonedim)|Bir tek boyutlu öğelerin sayısını değiştirir `COleSafeArray` nesnesi.|  
|[COleSafeArray::UnaccessData](#unaccessdata)|Azaltır kilit sayısı bir dizi ve işaretçiyi tarafından alınan geçersiz kılar `AccessData`.|  
|[COleSafeArray::Unlock](#unlock)|Azaltır kilit sayısı bir dizi bunu serbest veya yeniden boyutlandırılabilir.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[COleSafeArray::operator LPCVARIANT](#operator_lpcvariant)|Erişen temel **değişken** yapısını `COleSafeArray` nesnesi.|  
|[COleSafeArray::operator LPVARIANT](#operator_lpvariant)|Erişen temel **değişken** yapısını `COleSafeArray` nesnesi.|  
|[COleSafeArray::operator =](#operator_eq)|Kopyalar değerlere bir `COleSafeArray` nesne ( **SAFEARRAY**, **değişken**, `COleVariant`, veya `COleSafeArray` array).|  
|[COleSafeArray::operator ==](#operator_eq_eq)|İki değişken dizisi karşılaştırır ( **SAFEARRAY**, **değişken**, `COleVariant`, veya `COleSafeArray` Diziler).|  
|[COleSafeArray::operator&lt;&lt;](#operator_lt_lt)|İçeriğini çıkarır bir `COleSafeArray` döküm bağlam nesnesi.|  
  
## <a name="remarks"></a>Açıklamalar  
 `COleSafeArray`OLE türetilen **değişken** yapısı. OLE **SAFEARRAY** üye işlevleri aracılığıyla kullanılabilen `COleSafeArray`yanı üye işlevleri bayt tek boyutlu diziler için özel olarak tasarlanmış bir dizi olarak.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tagVARIANT`  
  
 `COleSafeArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxdisp.h  
  
##  <a name="accessdata"></a>COleSafeArray::AccessData  
 Dizi veri için bir işaretçi alır.  
  
```  
void AccessData(void** ppvData);
```  
  
### <a name="parameters"></a>Parametreler  
 `ppvData`  
 Dizi veri için bir işaretçi bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#26](../../mfc/codesnippet/cpp/colesafearray-class_1.cpp)]  
  
##  <a name="allocdata"></a>COleSafeArray::AllocData  
 Bellek için güvenli diziye ayırır.  
  
```  
void AllocData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="allocdescriptor"></a>COleSafeArray::AllocDescriptor  
 Bellek için güvenli diziye tanımlayıcısı ayırır.  
  
```  
void AllocDescriptor(DWORD dwDims);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDims`  
 Güvenli dizi boyutları sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="attach"></a>COleSafeArray::Attach  
 Var olan verileri denetimin verir **değişken** için dizi `COleSafeArray` nesnesi.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 *varSrc*  
 A **değişken** nesnesi. *VarSrc* parametre olmalıdır [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4)**VT_ARRAY**.  
  
### <a name="remarks"></a>Açıklamalar  
 Kaynak **değişken**'s türü ayarlanmış `VT_EMPTY`. Bu işlev, varsa geçerli dizi verileri temizler.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="clear"></a>COleSafeArray::Clear  
 Güvenli dizi temizler.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlayarak güvenli bir dizi işlev temizler `VARTYPE` nesnenin `VT_EMPTY`. İçeriğiyle yayımlanan ve dizi serbest bırakılır.  
  
##  <a name="colesafearray"></a>COleSafeArray::COleSafeArray  
 Oluşturan bir `COleSafeArray` nesnesi.  
  
```  
COleSafeArray();

 
COleSafeArray(
    const SAFEARRAY& saSrc,
    VARTYPE vtSrc);

 
COleSafeArray(
    LPCSAFEARRAY pSrc,
    VARTYPE vtSrc);  
  
COleSafeArray(const COleSafeArray& saSrc);  
COleSafeArray(const VARIANT& varSrc);  
  COleSafeArray(LPCVARIANT pSrc);  
COleSafeArray(const COleVariant& varSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `saSrc`  
 Var olan `COleSafeArray` nesne veya **SAFEARRAY** yeni içine kopyalanacak `COleSafeArray` nesnesi.  
  
 `vtSrc`  
 **VARTYPE** yeni `COleSafeArray` nesnesi.  
  
 `psaSrc`  
 Bir işaretçi bir **SAFEARRAY** yeni içine kopyalanacak `COleSafeArray` nesnesi.  
  
 *varSrc*  
 Var olan **değişken** veya `COleVariant` yeni içine kopyalanacak nesne `COleSafeArray` nesne.  
  
 `pSrc`  
 Bir işaretçi bir **değişken** yeni içine kopyalanacak nesne `COleSafeArray` nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Tüm bu oluşturucular Yeni Oluştur `COleSafeArray` nesneleri. Hiçbir parametre boş ise `COleSafeArray` nesnesi oluşturulur ( `VT_EMPTY`). Varsa `COleSafeArray` diğerinden kopyalanır, dizi [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) örtük olarak bilinen (bir `COleSafeArray`, `COleVariant`, veya **değişken**), **VARTYPE** , Kaynak dizi korunur ve belirtilmemesi. Varsa `COleSafeArray` diğerinden kopyalanır, dizi **VARTYPE** bilinmiyor ( **SAFEARRAY**), **VARTYPE** belirtilmelidir `vtSrc` parametresi.  
  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="copy"></a>COleSafeArray::Copy  
 Varolan bir güvenli dizisinin bir kopyasını oluşturur.  
  
```  
void Copy(LPSAFEARRAY* ppsa);
```  
  
### <a name="parameters"></a>Parametreler  
 *ppsa*  
 Yeni dizi tanımlayıcısı döndürmek bir konum işaretçisi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="create"></a>COleSafeArray::Create  
 Ayırır ve dizi veri başlatır.  
  
```  
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    DWORD* rgElements);

 
void Create(
    VARTYPE vtSrc,  
    DWORD dwDims,  
    SAFEARRAYBOUND* rgsabounds);
```  
  
### <a name="parameters"></a>Parametreler  
 `vtSrc`  
 Dizi temel türü (diğer bir deyişle, **VARTYPE** dizinin her öğesinin). **VARTYPE** VARIANT türleri bir kısmı için kısıtlanmış. Ne **VT_ARRAY** veya **VT_BYREF** bayrak ayarlanabilir. `VT_EMPTY`ve **VT_NULL** dizisi için geçerli temel türleri değildir. Tüm diğer yasal türleridir.  
  
 `dwDims`  
 Dizi boyutları sayısı. Dizi ile oluşturulduktan sonra bu değiştirilebilir [Redim](#redim).  
  
 *rgElements*  
 Dizideki her boyut için öğelerinin sayısı dizisi işaretçi.  
  
 *rgsabounds*  
 Vektör sınırlarının (her boyut için bir tane) işaretçi dizi için ayrılamadı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev geçerli dizi veri gerekirse temizler. Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="createonedim"></a>COleSafeArray::CreateOneDim  
 Yeni bir tek boyutlu `COleSafeArray` nesnesi.  
  
```  
void CreateOneDim(
    VARTYPE vtSrc,  
    DWORD dwElements,  
    const void* pvSrcData = NULL,  
    long nLBound = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `vtSrc`  
 Dizi temel türü (diğer bir deyişle, **VARTYPE** dizinin her öğesinin).  
  
 `dwElements`  
 Dizideki öğelerin sayısı. Dizi ile oluşturulduktan sonra bu değiştirilebilir [ResizeOneDim](#resizeonedim).  
  
 `pvSrcData`  
 Diziye kopyalamak için verileri işaretçi.  
  
 *nLBound*  
 Dizinin alt sınır.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlev ayırır ve verileri, belirtilen veri kopyalama dizi başlatır işaretçinin `pvSrcData` değil **NULL**.  
  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#28](../../mfc/codesnippet/cpp/colesafearray-class_3.cpp)]  
  
##  <a name="destroy"></a>COleSafeArray::Destroy  
 Var olan bir dizi tanımlayıcısı ve dizisindeki tüm veriler yok eder.  
  
```  
void Destroy();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesneleri dizideki depolanıyorsa, her nesne serbest bırakılır. Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydata"></a>COleSafeArray::DestroyData  
 Güvenli bir dizi tüm veriler yok eder.  
  
```  
void DestroyData();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Nesneleri dizideki depolanıyorsa, her nesne serbest bırakılır. Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="destroydescriptor"></a>COleSafeArray::DestroyDescriptor  
 Güvenli bir dizi tanımlayıcısının bozar.  
  
```  
void DestroyDescriptor();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="detach"></a>COleSafeArray::Detach  
 Ayırır **değişken** verilerden `COleSafeArray` nesnesi.  
  
```  
VARIANT Detach();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Arka plandaki **değişken** değeri `COleSafeArray` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Ayarlayarak güvenli diziye verilerde işlevi ayırır [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) nesnenin `VT_EMPTY`. Windows işlevini çağırarak dizi boşaltmak için çağıranın sorumluluğu olan [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835).  
  
 Hata üzerinde işlevi oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleSafeArray::PutElement](#putelement).  
  
##  <a name="getbytearray"></a>COleSafeArray::GetByteArray  
 Güvenli diziye içeriğini kopyalar bir `CByteArray`.  
  
```  
void GetByteArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Parametreler  
 `bytes`  
 Bir başvuru bir [CLongBinary](../../mfc/reference/cbytearray-class.md) nesnesi.  
  
##  <a name="getdim"></a>COleSafeArray::GetDim  
 Boyutlar sayısını döndürür `COleSafeArray` nesnesi.  
  
```  
DWORD GetDim();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenli dizi boyutları sayısı.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#27](../../mfc/codesnippet/cpp/colesafearray-class_2.cpp)]  
  
##  <a name="getelement"></a>COleSafeArray::GetElement  
 Güvenli dizinin tek bir öğesi alır.  
  
```  
void GetElement(
    long* rgIndices,  
    void* pvData);
```  
  
### <a name="parameters"></a>Parametreler  
 `rgIndices`  
 Bir dizinin her boyut için dizin dizi işaretçi.  
  
 `pvData`  
 Dizinin öğesi yerleştirileceği konuma işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev otomatik olarak windows işlevlerini çağıran `SafeArrayLock` ve `SafeArrayUnlock` önce ve sonra öğe alınıyor. Veri öğesi bir dize, nesne veya değişken işlevi öğesi doğru şekilde kopyalar. Parametre `pvData` büyük bir öğe içermesi için yeterli arabellek işaret etmelidir.  
  
 Hata üzerinde işlevi oluşturur bir [CMemoryException](../../mfc/reference/cmemoryexception-class.md) veya [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#29](../../mfc/codesnippet/cpp/colesafearray-class_4.cpp)]  
  
##  <a name="getelemsize"></a>COleSafeArray::GetElemSize  
 Bir öğedeki boyutunu alır bir `COleSafeArray` nesnesi.  
  
```  
DWORD GetElemSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güvenli bir dizi öğelerinin bayt cinsinden boyutu.  
  
##  <a name="getlbound"></a>COleSafeArray::GetLBound  
 Herhangi bir boyutu alt sınırı döndüren bir `COleSafeArray` nesnesi.  
  
```  
void GetLBound(
    DWORD dwDim,  
    long* pLBound);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDim`  
 Dizi boyutu alt sınırı almak istediğiniz.  
  
 *pLBound*  
 Alt sınır döndürülecek konuma işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#30](../../mfc/codesnippet/cpp/colesafearray-class_5.cpp)]  
  
##  <a name="getonedimsize"></a>COleSafeArray::GetOneDimSize  
 Tek boyutlu içinde öğe sayısını döndürür `COleSafeArray` nesnesi.  
  
```  
DWORD GetOneDimSize();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tek boyutlu güvenli dizideki öğelerin sayısı.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="getubound"></a>COleSafeArray::GetUBound  
 Herhangi bir güvenli bir dizi boyutu üst sınırı döndürür.  
  
```  
void GetUBound(
    DWORD dwDim,  
    long* pUBound);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwDim`  
 Dizi boyutu üst sınırı almak istediğiniz.  
  
 *pUBound*  
 Üst sınır döndürülecek konuma işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Hata üzerinde işlevi oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCOleContainer#31](../../mfc/codesnippet/cpp/colesafearray-class_6.cpp)]  
  
##  <a name="lock"></a>COleSafeArray::Lock  
 Bir dizi ve yeri dizi tanımlayıcısındaki dizi veri için bir işaretçi kilit sayısını artırır.  
  
```  
void Lock();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu hata hakkında oluşturur bir [COleException](../../mfc/reference/coleexception-class.md).  
  
 Dizi tanımlayıcısındaki işaretçi geçerliliğinin `Unlock` olarak adlandırılır. Çağrılar `Lock` iç içe olabilir; çağrıları eşit sayıda `Unlock` gereklidir.  
  
 Kilitliyken bir dizi silinemiyor.  
  
##  <a name="operator_lpcvariant"></a>COleSafeArray::operator LPCVARIANT  
 Arka plandaki erişmek için bu atama işleci çağrısı **değişken** yapısı bu `COleSafeArray` nesnesi.  
  
```  
operator LPCVARIANT() const;  
```  
  
##  <a name="operator_lpvariant"></a>COleSafeArray::operator LPVARIANT  
 Arka plandaki erişmek için bu atama işleci çağrısı **değişken** yapısı bu `COleSafeArray` nesnesi.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Açıklamalar  
 Bu değeri değiştirme Not **değişken** bu işlev tarafından döndürülen işaretçi tarafından erişilen yapısı, bu değeri değiştirir `COleSafeArray` nesnesi.  
  
##  <a name="operator_eq"></a>COleSafeArray::operator =  
 Bu aşırı yüklenmiş atama işleçleri kaynak değeri bu kopyalamak `COleSafeArray` nesnesi.  
  
```  
COleSafeArray& operator=(const COleSafeArray& saSrc);  
COleSafeArray& operator=(const VARIANT& varSrc);  
  COleSafeArray& operator=(LPCVARIANT pSrc);  
COleSafeArray& operator=(const COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Her işleç kısa bir açıklamasını aşağıdaki gibidir:  
  
- **işleç = (** *saSrc* **)** kopyalar varolan `COleSafeArray` bu nesne nesnesine.  
  
- **işleç = (** *varSrc***)** kopyalar varolan **değişken** veya `COleVariant` bu nesne dizisine.  
  
- **işleç = (** `pSrc` **)** kopya **değişken** dizi nesnesi tarafından erişilen `pSrc` bu nesne içinde.  
  
##  <a name="operator_eq_eq"></a>COleSafeArray::operator ==  
 Bu işleç dizilerinin karşılaştırır ( **SAFEARRAY**, **değişken**, `COleVariant`, veya `COleSafeArray` Diziler) ve olmaları durumunda eşit; Aksi halde 0 sıfır olmayan bir değer döndürür.  
  
```  
BOOL operator==(const SAFEARRAY& saSrc) const;  BOOL operator==(LPCSAFEARRAY pSrc) const;  
   
BOOL operator==(const COleSafeArray& saSrc) const;  BOOL operator==(const VARIANT& varSrc) const;  
   
BOOL operator==(LPCVARIANT pSrc) const;  BOOL operator==(const COleVariant& varSrc) const;  ```  
  
### Remarks  
 Two arrays are equal if they have an equal number of dimensions, equal size in each dimension, and equal element values.  
  
##  <a name="operator_lt_lt"></a>  COleSafeArray::operator &lt;&lt;  
 The `COleSafeArray` insertion (<<) operator supports diagnostic dumping and storing of a `COleSafeArray` object to an archive.  
  
```  
CDumpContext & AFXAPI işleci << (CDumpContext & dc,  
    COleSafeArray & saSrc);
```  
  
##  <a name="ptrofindex"></a>  COleSafeArray::PtrOfIndex  
 Returns a pointer to the element specified by the index values.  
  
```  
void PtrOfIndex (uzun * rgIndices,  
    void ** ppvData);
```  
  
### Parameters  
 `rgIndices`  
 An array of index values that identify an element of the array. All indexes for the element must be specified.  
  
 `ppvData`  
 On return, pointer to the element identified by the values in `rgIndices`.  
  
##  <a name="putelement"></a>  COleSafeArray::PutElement  
 Assigns a single element into the array.  
  
```  
void PutElement (uzun * rgIndices,  
    void * pvData);
```  
  
### Parameters  
 `rgIndices`  
 Pointer to an array of indexes for each dimension of the array.  
  
 `pvData`  
 Pointer to the data to assign to the array. **VT_DISPATCH**, **VT_UNKNOWN**, and `VT_BSTR` variant types are pointers and do not require another level of indirection.  
  
### Remarks  
 This function automatically calls the Windows functions [SafeArrayLock](https://msdn.microsoft.com/library/windows/desktop/ms221492.aspx) and [SafeArrayUnlock](https://msdn.microsoft.com/library/windows/desktop/ms221246.aspx) before and after assigning the element. If the data element is a string, object, or variant, the function copies it correctly, and if the existing element is a string, object, or variant, it is cleared correctly.  
  
 Note that you can have multiple locks on an array, so you can put elements into an array while the array is locked by other operations.  
  
 On error, the function throws a [CMemoryException](../../mfc/reference/cmemoryexception-class.md) or [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
 [!code-cpp[NVC_MFCOleContainer#32](../../mfc/codesnippet/cpp/colesafearray-class_7.cpp)]  
  
##  <a name="redim"></a>  COleSafeArray::Redim  
 Changes the least significant (rightmost) bound of a safe array.  
  
```  
void Redim (SAFEARRAYBOUND * psaboundNew);
```  
  
### Parameters  
 *psaboundNew*  
 Pointer to a new safe array bound structure containing the new array bound. Only the least significant dimension of an array may be changed.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
##  <a name="resizeonedim"></a>  COleSafeArray::ResizeOneDim  
 Changes the number of elements in a one-dimensional `COleSafeArray` object.  
  
```  
void ResizeOneDim (DWORD dwElements);
```  
  
### Parameters  
 `dwElements`  
 Number of elements in the one-dimensional safe array.  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::CreateOneDim](#createonedim).  
  
##  <a name="unaccessdata"></a>  COleSafeArray::UnaccessData  
 Decrements the lock count of an array and invalidates the pointer retrieved by `AccessData`.  
  
```  
void UnaccessData();
```  
  
### Remarks  
 On error, the function throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
### Example  
  See the example for [COleSafeArray::AccessData](#accessdata).  
  
##  <a name="unlock"></a>  COleSafeArray::Unlock  
 Decrements the lock count of an array so it can be freed or resized.  
  
```  
void Unlock();
```  
  
### Remarks  
 This function is called after access to the data in an array is finished. On error, it throws a [COleException](../../mfc/reference/coleexception-class.md).  
  
## See Also  
 [Hierarchy Chart](../../mfc/hierarchy-chart.md)   
 [COleVariant Class](../../mfc/reference/colevariant-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)
