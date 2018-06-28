---
title: CObArray sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CObArray
- AFXCOLL/CObArray
- AFXCOLL/CObArray::CObArray
- AFXCOLL/CObArray::Add
- AFXCOLL/CObArray::Append
- AFXCOLL/CObArray::Copy
- AFXCOLL/CObArray::ElementAt
- AFXCOLL/CObArray::FreeExtra
- AFXCOLL/CObArray::GetAt
- AFXCOLL/CObArray::GetCount
- AFXCOLL/CObArray::GetData
- AFXCOLL/CObArray::GetSize
- AFXCOLL/CObArray::GetUpperBound
- AFXCOLL/CObArray::InsertAt
- AFXCOLL/CObArray::IsEmpty
- AFXCOLL/CObArray::RemoveAll
- AFXCOLL/CObArray::RemoveAt
- AFXCOLL/CObArray::SetAt
- AFXCOLL/CObArray::SetAtGrow
- AFXCOLL/CObArray::SetSize
dev_langs:
- C++
helpviewer_keywords:
- CObArray [MFC], CObArray
- CObArray [MFC], Add
- CObArray [MFC], Append
- CObArray [MFC], Copy
- CObArray [MFC], ElementAt
- CObArray [MFC], FreeExtra
- CObArray [MFC], GetAt
- CObArray [MFC], GetCount
- CObArray [MFC], GetData
- CObArray [MFC], GetSize
- CObArray [MFC], GetUpperBound
- CObArray [MFC], InsertAt
- CObArray [MFC], IsEmpty
- CObArray [MFC], RemoveAll
- CObArray [MFC], RemoveAt
- CObArray [MFC], SetAt
- CObArray [MFC], SetAtGrow
- CObArray [MFC], SetSize
ms.assetid: 27894efd-2370-4776-9ed9-24a98492af17
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 41165f177671379eecbc700df016cd19aea69962
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/27/2018
ms.locfileid: "37040213"
---
# <a name="cobarray-class"></a>CObArray sınıfı
Dizileri destekler `CObject` işaretçileri.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CObArray : public CObject  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::CObArray](#cobarray)|İçin boş bir dizi oluşturur `CObject` işaretçileri.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::Add](#add)|Bir öğeyi dizinin sonuna ekler; dizi gerekirse artar.|  
|[CObArray::Append](#append)|Başka bir dizi diziye ekler; dizi gerekirse artar.|  
|[CObArray::Copy](#copy)|Başka bir dizi diziye kopyalar; dizi gerekirse artar.|  
|[CObArray::ElementAt](#elementat)|Dizi öğesi işaretçinin geçici bir başvuru döndürür.|  
|[CObArray::FreeExtra](#freeextra)|Geçerli bir üst sınır yukarıdaki tüm kullanılmayan belleği serbest bırakır.|  
|[CObArray::GetAt](#getat)|Belirtilen dizindeki değeri döndürür.|  
|[CObArray::GetCount](#getcount)|Bu dizide öğe sayısını alır.|  
|[CObArray::GetData](#getdata)|Dizideki öğelere erişim sağlar. Olabilir **NULL**.|  
|[CObArray::GetSize](#getsize)|Bu dizide öğe sayısını alır.|  
|[CObArray::GetUpperBound](#getupperbound)|En büyük geçerli dizinini döndürür.|  
|[CObArray::InsertAt](#insertat)|Bir öğenin (veya başka bir dizinin tüm öğeleri) belirtilen bir dizinde ekler.|  
|[CObArray::IsEmpty](#isempty)|Dizi boş olup olmadığını belirler.|  
|[CObArray::RemoveAll](#removeall)|Bu dizisinden tüm öğeleri kaldırır.|  
|[CObArray::RemoveAt](#removeat)|Belirli bir dizinindeki bir öğeyi kaldırır.|  
|[CObArray::SetAt](#setat)|Belirli bir dizine için değeri ayarlar; dizi büyümeye izin verilmiyor.|  
|[CObArray::SetAtGrow](#setatgrow)|Belirli bir dizine için değeri ayarlar; dizi gerekirse artar.|  
|[CObArray::SetSize](#setsize)|Bu dizide dahil edilmek üzere öğe sayısını ayarlar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CObArray::operator]](#operator_at)|Belirtilen dizindeki öğeyi alır veya ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu nesne dizileri C diziler için benzer ancak dinamik olarak küçültmek ve gerektikçe büyütün.  
  
 Dizi dizinleri her zaman 0 konumunda başlatın. Üst sınır düzeltin veya dizi öğeleri geçerli sınır geçmiş eklediğinizde genişletmek izin vermek karar verebilirsiniz. Bazı öğeler null olsa bile bellek üst sınırı için bitişik ayrılır.  
  
 Win32, boyutu altında bir `CObArray` nesne yalnızca kullanılabilir bellek sınırlıdır.  
  
 Bir C dizi için erişim süresi ile bir `CObArray` dizinli öğe sabit öğesidir ve dizi boyutundan bağımsızdır.  
  
 `CObArray` ımplement_serıal makrosu seri hale getirme ve alt öğeleri dökme desteklemek için bir araya getirir. Bir dizi varsa `CObject` işaretçileri aşırı yüklenmiş ekleme işleciyle veya ile bir arşivde saklanır `Serialize` her üye işlev `CObject` öğesi buna karşılık, seri hale getirilmiş yanı sıra, dizi dizini.  
  
 Tek bir dökümü gerekiyorsa `CObject` bir dizideki öğeler, derinliğini ayarlamanız gerekir `CDumpContext` nesnesine 1 veya daha büyük.  
  
 Zaman bir `CObArray` Nesne silindiğinden veya ne zaman öğeleri kaldırılır, yalnızca `CObject` işaretçileri kaldırılır, nesneleri başvuruyor.  
  
> [!NOTE]
>  Bir dizi kullanmadan önce kullanın `SetSize` boyutuna kurmak ve bunun için bellek ayrılamadı. Kullanmıyorsanız, `SetSize`, dizinizi için öğe eklemek görüntülenmesine neden olur sık bırakılan ve kopyalanır. Sık sık yeniden ayırma ve kopyalama verimsiz ve bellek parçalara.  
  
 Array sınıfı türetme listesi türetme benzer. Özel amaçlı listesi sınıfı türetme hakkında daha fazla bilgi için bkz: [koleksiyonları](../../mfc/collections.md).  
  
> [!NOTE]
>  Dizi seri hale getirmek istiyorsanız, türetilmiş sınıf uygulamasında ımplement_serıal makrosu kullanmanız gerekir.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CObArray`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcoll.h  
  
##  <a name="add"></a>  CObArray::Add  
 1 ile dizi büyüyen bir dizinin sonuna yeni bir öğe ekler.  
  
```  
INT_PTR Add(CObject* newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *newElement*  
 `CObject` Bu diziye eklenecek işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Eklenen öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa [SetSize](#setsize) ile kullanılan bir *nGrowBy* 1 sonra ek bellek büyük bir değer ayrılamadı. Ancak, üst sınır tarafından yalnızca 1 artacaktır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::Add`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**INT_PTR ekleyin (bayt** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR ekleyin (DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR ekleyin (void\***  `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR ekleme (LPCTSTR** `newElement` **); throw (CMemoryException\* );**<br /><br /> **INT_PTR Add(const CString&** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR ekleyin (UINT** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR ekleme (WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#75](../../mfc/codesnippet/cpp/cobarray-class_1.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `Add example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $442A 21`  
  
 `[1] = a CAge at $4468 40`  
  
##  <a name="append"></a>  CObArray::Append  
 Başka bir dizinin içeriğini verilen dizi sonuna eklemek için bu üye işlevini çağırın.  
  
```  
INT_PTR Append(const CObArray& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kaynak dizisine eklenecek öğe.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk eklenmiş öğenin dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Diziler, aynı türde olmalıdır.  
  
 Gerekirse, `Append` diziye eklenen öğeleri yerleştirmek için ek bellek ayırabilir.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::Append`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**INT_PTR ekleme (const CLongBinary &** *src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR ekleme (const CDWordArray &** *src* **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR ekleme (const CPtrArray &** *src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR ekleme (const CStringArray &** *src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR ekleme (const CUIntArray &** *src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR ekleme (const CWordArray &** *src* **);**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#76](../../mfc/codesnippet/cpp/cobarray-class_2.cpp)]  
  
##  <a name="copy"></a>  CObArray::Copy  
 Verilen dizi öğeleri aynı türde başka bir dizinin öğeleri üzerine yazmak için bu üye işlevini çağırın.  
  
```  
void Copy(const CObArray& src);
```  
  
### <a name="parameters"></a>Parametreler  
 *src*  
 Kaynak diziye kopyalanacak öğe.  
  
### <a name="remarks"></a>Açıklamalar  
 `Copy` belleği serbest değil; Ancak, gerekirse, `Copy` diziye kopyalanan öğelerin uyum sağlamak için ek bellek ayırabilir.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::Copy`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**Geçersiz kopya (const CLongBinary &** *src* **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**Geçersiz kopya (const CDWordArray &** *src* **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**Geçersiz kopya (const CPtrArray &** *src* **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**Geçersiz kopya (const CStringArray &** *src* **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**Geçersiz kopya (const CUIntArray &** *src* **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**Geçersiz kopya (const CWordArray &** *src* **);**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#77](../../mfc/codesnippet/cpp/cobarray-class_3.cpp)]  
  
##  <a name="cobarray"></a>  CObArray::CObArray  
 Boş bir yapıları `CObject` işaretçi dizi.  
  
```  
CObArray();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi bir öğe aynı anda artar.  
  
 Aşağıdaki tabloda benzer diğer oluşturucular gösterilmektedir `CObArray::CObArray`.  
  
|örneği|Oluşturucu|  
|-----------|-----------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**CLongBinary ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**CDWordArray ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**CPtrArray ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CStringArray ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**CUIntArray ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**CWordArray ();**|  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_MFCCollections#78](../../mfc/codesnippet/cpp/cobarray-class_4.cpp)]  
  
##  <a name="elementat"></a>  CObArray::ElementAt  
 Dizi öğesi işaretçinin geçici bir başvuru döndürür.  
  
```  
CObject*& ElementAt(INT_PTR nIndex);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `GetUpperBound`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir başvuru bir `CObject` işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Diziler için sol taraftaki atama işleci uygulamak için kullanılır. Bu yalnızca özel dizi işleçler için kullanılması gereken gelişmiş bir işlevi olduğunu unutmayın.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::ElementAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**BAYT & ElementAt (INT_PTR** `nIndex` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & ElementAt (INT_PTR** `nIndex` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& ElementAt (INT_PTR** `nIndex` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & ElementAt (INT_PTR** `nIndex` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & ElementAt (INT_PTR** `nIndex` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & ElementAt (INT_PTR** `nIndex` **);**|  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CObArray::GetSize](#getsize).  
  
##  <a name="freeextra"></a>  CObArray::FreeExtra  
 Dizi büyütülen sırada ayrılmış ek bellek boşaltır.  
  
```  
void FreeExtra();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlev boyutunu veya dizi üst sınırının üzerinde etkisi yoktur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::FreeExtra`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void FreeExtra ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void FreeExtra ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void FreeExtra ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void FreeExtra ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void FreeExtra ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void FreeExtra ();**|  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CObArray::GetData](#getdata).  
  
##  <a name="getat"></a>  CObArray::GetAt  
 Belirtilen dizindeki dizi öğesi döndürür.  
  
```  
CObject* GetAt(INT_PTR nIndex) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `GetUpperBound`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `CObject` Şu anda bu dizinindeki işaretçi öğe.  
  
### <a name="remarks"></a>Açıklamalar  
  
> [!NOTE]
>  Negatif bir değer veya bir değer tarafından döndürülen değeri büyük geçirme `GetUpperBound` içinde başarısız onaylama neden olur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::GetAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**BAYT GetAt (INT_PTR** `nIndex` **) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD GetAt (INT_PTR** `nIndex` **) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\* GetAt (INT_PTR** `nIndex` **) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString GetAt (INT_PTR** `nIndex` **) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT GetAt (INT_PTR** `nIndex` **) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD GetAt (INT_PTR** `nIndex` **) const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#79](../../mfc/codesnippet/cpp/cobarray-class_5.cpp)]  
  
##  <a name="getcount"></a>  CObArray::GetCount  
 Dizi öğe sayısını döndürür.  
  
```  
INT_PTR GetCount() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizideki öğelerin sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizideki öğelerin sayısını almak için bu yöntemi çağırın. Dizinleri sıfır tabanlı olduğundan, 1'den büyük dizin büyük boyutudur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::GetCount`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetCount () const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetCount () const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetCount () const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetCount () const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetCount () const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetCount () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#80](../../mfc/codesnippet/cpp/cobarray-class_6.cpp)]  
  
##  <a name="getdata"></a>  CObArray::GetData  
 Dizideki öğeler doğrudan erişmek için bu üye işlevini kullanın.  
  
```  
const CObject** GetData() const;  
  
CObject** GetData();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi için bir işaretçi `CObject` işaretçileri.  
  
### <a name="remarks"></a>Açıklamalar  
 Öğe varsa, `GetData` null değeri döndürür.  
  
 Dizi öğelerini doğrudan erişim daha hızlı çalışmanıza yardımcı olabilir, ancak çağrılırken dikkatli `GetData`; doğrudan yaptığınız herhangi bir hata dizinizi öğelerini etkiler.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::GetData`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**const bayt\* GetData () const; BAYT\* GetData ();**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**const DWORD\* GetData const (); DWORD\* GetData ();**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**const void\* \* GetData () const; void\* \* GetData ();**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**const CString\* GetData () const; CString\* GetData ();**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**const UINT\* GetData () const; UINT\* GetData ();**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**const WORD\* GetData () const; WORD\* GetData ();**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#81](../../mfc/codesnippet/cpp/cobarray-class_7.cpp)]  
  
##  <a name="getsize"></a>  CObArray::GetSize  
 Dizinin boyutu döndürür.  
  
```  
INT_PTR GetSize() const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizinleri sıfır tabanlı olduğundan, 1'den büyük dizin büyük boyutudur.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::GetSize`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetSize () const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetSize () const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetSize () const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetSize () const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetSize () const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetSize () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#82](../../mfc/codesnippet/cpp/cobarray-class_8.cpp)]  
  
##  <a name="getupperbound"></a>  CObArray::GetUpperBound  
 Bu dizinin geçerli üst sınırının döndürür.  
  
```  
INT_PTR GetUpperBound() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Üst sınır (sıfır tabanlı) dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi dizinleri sıfır tabanlı olduğundan, bu işlev, 1 değerini döndürür. değerinden `GetSize`.  
  
 Koşul **GetUpperBound ()** = -1 gösterir dizi öğe içeriyor.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::GetUpperBound`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**INT_PTR GetUpperBound () const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**INT_PTR GetUpperBound () const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#83](../../mfc/codesnippet/cpp/cobarray-class_9.cpp)]  
  
##  <a name="insertat"></a>  CObArray::InsertAt  
 Bir öğenin (veya başka bir dizinin tüm öğeleri) belirtilen bir dizinde ekler.  
  
```  
void InsertAt(
    INT_PTR nIndex,  
    CObject* newElement,  
    INT_PTR nCount = 1);

 
void InsertAt(
    INT_PTR nStartIndex,  
    CObArray* pNewArray);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `GetUpperBound`.  
  
 *newElement*  
 `CObject` Bu dizide yerleştirilecek işaretçi. A *newElement* değerinin **NULL** izin verilir.  
  
 *nCount*  
 Bu öğe olmalıdır sayısı (varsayılan 1) ekledi.  
  
 *nStartIndex*  
 Tarafından döndürülen değeri,'den büyük bir tamsayı dizini `GetUpperBound`.  
  
 *pNewArray*  
 Bu diziye eklenecek öğeleri içeren başka bir dizi.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk sürümü `InsertAt` bir öğenin (veya birden çok kopya, bir öğenin) bir dizi belirtilen dizinde ekler. İşlem sırasında yapılandırmasına kayar (dizini artırılarak) ve bu dizin mevcut öğede üzerindeki tüm öğeleri yukarı kaydırır.  
  
 İkinci Sürüm tüm öğeleri diğerinden ekler `CObArray` başlayarak koleksiyon *nStartIndex* konumu.  
  
 `SetAt` İşlevi, buna karşılık, bir belirtilen dizi öğesi değiştirir ve herhangi bir öğe shift değil.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::InsertAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, bayt** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CLongBinary\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, DWORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CDWordArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, void\***  `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CPtrArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CStringArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, UINT** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CUIntArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void InsertAt (INT_PTR** `nIndex` **, WORD** `newElement` **, int** `nCount` **= 1);**<br /><br /> **throw (CMemoryException\* );**<br /><br /> **void InsertAt (INT_PTR** `nStartIndex` **, CWordArray\***  `pNewArray` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#84](../../mfc/codesnippet/cpp/cobarray-class_10.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `InsertAt example: A CObArray with 3 elements`  
  
 `[0] = a CAge at $45C8 21`  
  
 `[1] = a CAge at $4646 30`  
  
 `[2] = a CAge at $4606 40`  
  
##  <a name="isempty"></a>  CObArray::IsEmpty  
 Dizi boş olup olmadığını belirler.  
  
```  
BOOL IsEmpty() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi boş ise sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="operator_at"></a>  CObArray::operator]  
 Bu alt simge işleçlerini için uygun bir alternatif olan `SetAt` ve `GetAt` işlevleri.  
  
```  
CObject*& operator[](int_ptr nindex);  
CObject* operator[](int_ptr nindex) const;  
```  
  
### <a name="remarks"></a>Açıklamalar  
 İlk işleci adlı olmayan diziler için **const**, sağ (r) veya Atama ifadesinin sol (l-değeri) üzerinde kullanılabilir. İkinci olarak adlandırılan için **const** dizileri, yalnızca sağ tarafta kullanılır.  
  
 Alt simge (ya da sol veya sağ tarafında Atama ifadesinin) sınırların dışında olup olmadığını kitaplığının hata ayıklama sürümü onaylar.  
  
 Aşağıdaki tabloda benzer diğer işleçleri gösterilmektedir **CObArray::operator []**.  
  
|örneği|İşleç|  
|-----------|--------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**BAYT & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **BYTE [] işleci (int_ptr** `nindex`  **\) const;**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**DWORD & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **DWORD [] işleci (int_ptr** `nindex`  **\) const;**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void\*& [] işleci (int_ptr** `nindex`  **\);**<br /><br /> **void\* [] işleci (int_ptr** `nindex`  **\) const;**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**CString & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **CString [] işleci (int_ptr** `nindex`  **\) const;**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**UINT & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **UINT [] işleci (int_ptr** `nindex`  **\) const;**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**WORD & işleci [] (int_ptr** `nindex`  **\);**<br /><br /> **WORD [] işleci (int_ptr** `nindex`  **\) const;**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#88](../../mfc/codesnippet/cpp/cobarray-class_11.cpp)]  
  
##  <a name="removeall"></a>  CObArray::RemoveAll  
 Bu dizisinden tüm işaretçiler kaldırır, ancak gerçekte silmediği `CObject` nesneleri.  
  
```  
void RemoveAll();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dizi zaten boşsa, işlev hala çalışmaktadır.  
  
 `RemoveAll` İşlevi işaretçisi depolama için kullanılan tüm belleği serbest bırakır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::RemoveAll`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void RemoveAll( );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAll( );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAll( );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAll( );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAll( );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAll( );**|  
  
### <a name="example"></a>Örnek  
 Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#85](../../mfc/codesnippet/cpp/cobarray-class_12.cpp)]  
  
##  <a name="removeat"></a>  CObArray::RemoveAt  
 Dizideki belirli bir dizinden başlayarak bir veya daha fazla öğeleri kaldırır.  
  
```  
void RemoveAt(
    INT_PTR nIndex,  
    INT_PTR nCount = 1);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `GetUpperBound`.  
  
 *nCount*  
 Kaldırılacak öğe sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 İşlem sırasında kaldırılan öğe yukarıdaki tüm öğeleri aşağı kaydırır. Bu üst dizisi bağlı ancak belleği serbest değil azaltır.  
  
 Dizideki kaldırma noktası yukarıda yer alan çok daha fazla öğe kaldırmayı deneyin, hata ayıklama sürümü kitaplığının onaylar.  
  
 `RemoveAt` İşlev kaldırır `CObject` dizi, ancak işaretçi nesnenin kendisini silmez.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::RemoveAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** `nCount` **= 1);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void RemoveAt (INT_PTR** `nIndex` **, INT_PTR** *nCount* **= 1);**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#112](../../mfc/codesnippet/cpp/cobarray-class_13.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `RemoveAt example: A CObArray with 1 elements`  
  
 `[0] = a CAge at $4606 40`  
  
##  <a name="setat"></a>  CObArray::SetAt  
 Dizi öğesi belirtilen dizindeki ayarlar.  
  
```  
void SetAt(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0 değerine eşit bir tamsayı dizini ve tarafından döndürülen değer eşit veya daha az `GetUpperBound`.  
  
 *newElement*  
 Bu dizide eklenecek nesne işaretçisi. A **NULL** değerine izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetAt` dizi büyümesine neden. Kullanım `SetAtGrow` otomatik olarak büyümeye dizi istiyorsanız.  
  
 Dizin değeri geçerli bir konum dizideki temsil ettiğini emin olmalısınız. Sınırların dışında olması durumunda kitaplığının hata ayıklama sürümü onaylar.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::SetAt`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void SetAt (INT_PTR** `nIndex` **, bayt** `newElement` **);**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, DWORD** `newElement` **);**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, void\***  `newElement` **);**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, UINT** `newElement` **);**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAt (INT_PTR** `nIndex` **, WORD** `newElement` **);**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#86](../../mfc/codesnippet/cpp/cobarray-class_14.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `SetAt example: A CObArray with 2 elements`  
  
 `[0] = a CAge at $47E0 30`  
  
 `[1] = a CAge at $47A0 40`  
  
##  <a name="setatgrow"></a>  CObArray::SetAtGrow  
 Dizi öğesi belirtilen dizindeki ayarlar.  
  
```  
void SetAtGrow(
    INT_PTR nIndex,  
    CObject* newElement);
```  
  
### <a name="parameters"></a>Parametreler  
 *nIndex*  
 Büyük veya 0 değerine eşit bir tamsayı dizini.  
  
 *newElement*  
 Bu diziye eklenecek nesne işaretçisi. A **NULL** değerine izin verilir.  
  
### <a name="remarks"></a>Açıklamalar  
 Gerekirse, dizi büyür (diğer bir deyişle, üst sınır yeni öğe uyum sağlayacak şekilde ayarlanır).  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::SetAtGrow`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, bayt** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, DWORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, void\***  `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, LPCTSTR** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, UINT** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetAtGrow (INT_PTR** `nIndex` **, WORD** `newElement` **);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Örnek  
  Bkz: [CObList::CObList](../../mfc/reference/coblist-class.md#coblist) listesini `CAge` tüm koleksiyon örneklerde kullanılan bir sınıftır.  
  
 [!code-cpp[NVC_MFCCollections#87](../../mfc/codesnippet/cpp/cobarray-class_15.cpp)]  
  
 Bu program sonuçlarından aşağıdaki gibidir:  
  
 `SetAtGrow example: A CObArray with 4 elements`  
  
 `[0] = a CAge at $47C0 21`  
  
 `[1] = a CAge at $4800 40`  
  
 `[2] = NULL`  
  
 `[3] = a CAge at $4840 65`  
  
##  <a name="setsize"></a>  CObArray::SetSize  
 Boş veya varolan bir dizide boyutunu belirler; Gerekirse, bellek ayırır.  
  
```  
void SetSize(
    INT_PTR nNewSize,  
    INT_PTR nGrowBy = -1);
```  
  
### <a name="parameters"></a>Parametreler  
 *nNewSize*  
 Yeni dizi boyutu (öğelerin sayısı). Büyük veya 0 değerine eşit olmalıdır.  
  
 *nGrowBy*  
 Öğe yuva boyutu artışı gerekliyse ayırmak için minimum sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni boyutu eski boyutundan daha küçükse, dizi kesilir ve tüm kullanılmayan belleği serbest bırakılır. Verimlilik için arama `SetSize` kullanmadan önce dizinin boyutunu ayarlamak için. Bu yeniden ayırın ve dizi bir öğe eklendiğinde kopyalamak için gereken önler.  
  
 *NGrowBy* parametre dizisi artan sırada iç bellek ayırma etkiler. Kullanımı hiçbir zaman tarafından bildirilen dizi boyutu etkiler `GetSize` ve `GetUpperBound`.  
  
 Dizinin boyutunu büyümüştür varsa, tüm yeni ayrılmış **CObject \***  işaretçileri NULL olarak ayarlanır.  
  
 Aşağıdaki tabloda, benzer işlevler diğer üye gösterilmektedir `CObArray::SetSize`.  
  
|örneği|Üye İşlevi|  
|-----------|---------------------|  
|[CLongBinary](../../mfc/reference/cbytearray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CDWordArray](../../mfc/reference/cdwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CPtrArray](../../mfc/reference/cptrarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CStringArray](../../mfc/reference/cstringarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CUIntArray](../../mfc/reference/cuintarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|  
|[CWordArray](../../mfc/reference/cwordarray-class.md)|**void SetSize (INT_PTR** `nNewSize` **, int** `nGrowBy` **= -1);**<br /><br /> **throw (CMemoryException\* );**|  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [CObArray::GetData](#getdata).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject sınıfı](../../mfc/reference/cobject-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CStringArray sınıfı](../../mfc/reference/cstringarray-class.md)   
 [CPtrArray sınıfı](../../mfc/reference/cptrarray-class.md)   
 [CLongBinary sınıfı](../../mfc/reference/cbytearray-class.md)   
 [CWordArray sınıfı](../../mfc/reference/cwordarray-class.md)   
 [CDWordArray Sınıfı](../../mfc/reference/cdwordarray-class.md)
