---
title: CSize sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
dev_langs:
- C++
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 18c48ccf2d1d7f424ca9b95f9dcbf7a2953a52aa
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="csize-class"></a>CSize sınıfı
Windows benzer [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) göreli koordinat veya konumu uygulayan yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSize : public tagSIZE 
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSize::CSize](#csize)|Oluşturan bir `CSize` nesnesi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSize::operator-](#operator_-)|İki boyutları çıkarır.|  
|[CSize::operator! =](#operator_neq)|Eşitsizlik arasında denetler `CSize` ve boyutu.|  
|[CSize::operator +](#operator_add)|İki boyutları ekler.|  
|[CSize::operator +=](#operator_add_eq)|Bir boyuta ekler `CSize`.|  
|[CSize::operator-=](#operator_-_eq)|Sabit boyutlu bir çıkarır `CSize`.|  
|[CSize::operator ==](#operator_eq_eq)|Denetler arasında eşitliği `CSize` ve boyutu.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıfın türetildiği **BOYUTU** yapısı. Bu, iletebilir anlamına gelir. bir `CSize` için çağıran bir parametreye bir **BOYUTU** ve veri üyeleri **BOYUTU** yapısı erişilebilir veri üyeleri olan `CSize`.  
  
 **Cx** ve **cy** üyeleri **BOYUTU** (ve `CSize`) ortaktır. Ayrıca, `CSize` işlemek için üye işlevleri uygulayan **BOYUTU** yapısı.  
  
> [!NOTE]
>  Daha fazla bilgi için paylaşılan yardımcı sınıflar (gibi `CSize`), bkz: [paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tagSIZE`  
  
 `CSize`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltypes.h  
  
##  <a name="csize"></a>  CSize::CSize  
 Oluşturan bir `CSize` nesnesi.  
  
```  
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw(); 
```  
  
### <a name="parameters"></a>Parametreler  
 *initCX*  
 Ayarlar **cx** üyesi için `CSize`.  
  
 *initCY*  
 Ayarlar **cy** üyesi için `CSize`.  
  
 `initSize`  
 [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya `CSize` başlatmak için kullanılan nesne `CSize`.  
  
 `initPt`  
 [NOKTASI](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` başlatmak için kullanılan nesne `CSize`.  
  
 `dwSize`  
 `DWORD` başlatmak için kullanılan `CSize`. Düşük düzey sözcük **cx** üyesi ve yüksek düzey word **cy** üyesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkenler verilirse, **cx** ve **cy** sıfır olarak başlatılır.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>  CSize::operator ==  
 Eşitlik iki boyutları arasında denetler.  
  
```   
BOOL operator==(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Boyutlar eşitse, sıfır olmayan döndürür, otherwize 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]  
  
##  <a name="operator_neq"></a>  CSize::operator! =  
 Eşitsizlik iki boyutları arasında denetler.  
  
```   
BOOL operator!=(SIZE size) const throw(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Boyutları eşit değilse sıfır olmayan döndürür Aksi halde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>  CSize::operator +=  
 Bunun için bir boyut ekler `CSize`.  
  
```   
void operator+=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>  CSize::operator-=  
 Bu boyutundan çıkarır `CSize`.  
  
```   
void operator-=(SIZE size) throw(); 
```  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]  
  
##  <a name="operator_add"></a>  CSize::operator +  
 Bu işleçlere bu eklemek `CSize` parametresinin değeri değerine.  
  
```   
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tek tek işleçleri aşağıdaki açıklamalarını bakın:  
  
- **operator + (** `size` **)** bu işlem iki ekler `CSize` değerleri.  
  
- **operator + (** `point` **)** bu işlemi (taşır) kaydırır bir [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) (veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) bu değerle `CSize` değeri. **Cx** ve **cy** bu üyeleri `CSize` değeri eklenir **x** ve **y** veri üyeleri **noktası**  değeri. Sürümüne paraleldir [CPoint::operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add) alan bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) parametresi.  
  
- **operator + (** `lpRect` **)** bu işlemi (taşır) kaydırır bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) (veya [CRect](../../atl-mfc-shared/reference/crect-class.md)) bu değerle `CSize` değeri. **Cx** ve **cy** bu üyeleri `CSize` değeri eklenir **sol**, **üst**, **sağ**, ve **alt** veri üyeleri `RECT` değeri. Sürümüne paraleldir [CRect::operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add) alan bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) parametresi.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]  
  
##  <a name="operator_-"></a>  CSize::operator-  
 Bu işleçlere ilk üç bu çıkarma `CSize` parametresinin değeri değerine.  
  
```   
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw(); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Dördüncü işleci birli, eksi işareti değiştirir `CSize` değeri. Tek tek işleçleri aşağıdaki açıklamalarını bakın:  
  
- **-işleci (** `size` **)** bu işlem iki çıkarır `CSize` değerleri.  
  
- **-işleci (** `point` **)** bu işlemi (taşır) kaydırır bir [noktası](http://msdn.microsoft.com/library/windows/desktop/dd162805) veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) bu ADDITIVE tersini değeriyle `CSize` değer. **Cx** ve **cy** bu `CSize` değer çıkarılır **x** ve **y** veri üyeleri **noktası**  değeri. Sürümüne paraleldir [CPoint::operator -](../../atl-mfc-shared/reference/cpoint-class.md#operator_-) alan bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) parametresi.  
  
- **-işleci (** `lpRect` **)** bu işlemi (taşır) kaydırır bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) veya [CRect](../../atl-mfc-shared/reference/crect-class.md) bu ADDITIVE tersini değeriyle `CSize` değeri. **Cx** ve **cy** bu üyeleri `CSize` değer çıkarılır **sol**, **üst**, **sağ**, ve **alt** veri üyeleri `RECT` değeri. Sürümüne paraleldir [CRect::operator -](../../atl-mfc-shared/reference/crect-class.md#operator_-) alan bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) parametresi.  
  
- **operator-()** bu işlem bu ADDITIVE tersini döndürür `CSize` değeri.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CRect sınıfı](../../atl-mfc-shared/reference/crect-class.md)   
 [CPoint Sınıfı](../../atl-mfc-shared/reference/cpoint-class.md)

