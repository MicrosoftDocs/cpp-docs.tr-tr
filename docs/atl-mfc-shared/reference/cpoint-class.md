---
title: CPoint sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
dev_langs:
- C++
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7140e2db55db8a28c1af63f89517708f4dc0d835
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cpoint-class"></a>CPoint sınıfı
Windows benzer `POINT` yapısı.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CPoint : public tagPOINT 
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPoint::CPoint](#cpoint)|Oluşturan bir `CPoint`.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPoint::Offset](#offset)|Değerleri ekler **x** ve **y** üyeleri `CPoint`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPoint::operator-](#operator_-)|Farkını döndürür bir `CPoint` ve bir boyut veya bir nokta ya da iki nokta veya uzaklık negatif bir boyuta göre boyutu birbirinden değilleme.|  
|[CPoint::operator! =](#operator_neq)|İki nokta arasındaki eşitsizlik denetler.|  
|[CPoint::operator +](#operator_add)|Toplamını döndürür bir `CPoint` ve boyutu veya de noktası veya bir `CRect` boyutuna göre uzaklığı.|  
|[CPoint::operator +=](#operator_add_eq)|Kaydırır `CPoint` boyutu veya noktası ekleyerek düzenleyin.|  
|[CPoint::operator-=](#operator_-_eq)|Kaydırır `CPoint` boyutu veya noktasının çıkarılarak tarafından.|  
|[CPoint::operator ==](#operator_eq_eq)|İki nokta arasındaki eşitlik denetler.|  
  
## <a name="remarks"></a>Açıklamalar  
 Ayrıca işlemek için üye işlevlerini içerir `CPoint` ve [noktası](../../mfc/reference/point-structure1.md) yapıları.  
  
 A `CPoint` nesnesi olabilir yerde kullanılan bir `POINT` yapısı kullanılır. "Boyutu" ile etkileşim operatörler, bu sınıfın ya da kabul [CSize](../../atl-mfc-shared/reference/csize-class.md) nesneleri veya [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapıları bu yana iki birbirinin yerine kullanılabilir.  
  
> [!NOTE]
>  Bu sınıfın türetildiği `tagPOINT` yapısı. (Adı `tagPOINT` için daha az kullanılan bir addır `POINT` yapısı.) Veri üyeleri buna `POINT` yapısı, `x` ve `y`, erişilebilir veri üyesi `CPoint`.  
  
> [!NOTE]
>  Daha fazla bilgi için paylaşılan yardımcı sınıflar (gibi `CPoint`), bkz: [paylaşılan sınıfları](../../atl-mfc-shared/atl-mfc-shared-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tagPOINT`  
  
 `CPoint`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atltypes.h  
  
##  <a name="cpoint"></a>CPoint::CPoint
 Oluşturan bir `CPoint` nesnesi.  
  
```  
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `initX`  
 Değerini belirtir. `x` üyesi `CPoint`.  
  
 `initY`  
 Değerini belirtir. `y` üyesi `CPoint`.  
  
 `initPt`  
 [NOKTASI](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` başlatmak için kullanılan değerleri belirtir `CPoint`.  
  
 `initSize`  
 [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) başlatmak için kullanılan değerleri belirtir `CPoint`.  
  
 `dwPoint`  
 Ayarlar `x` düşük düzey sözcüğün üyesine `dwPoint` ve `y` yüksek düzey sözcüğün üyesine `dwPoint`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bağımsız değişkenler verilirse, `x` ve `y` üyeleri 0 olarak ayarlanmış.  
  
### <a name="example"></a>Örnek  
  
```cpp   
CPoint   ptTopLeft(0, 0); 
// works from a POINT, too  
 
POINT   ptHere;  
ptHere.x = 35;  
ptHere.y = 95;  
 
CPoint   ptMFCHere(ptHere);
 
// works from a SIZE 
SIZE   sHowBig;  
sHowBig.cx = 300;  
sHowBig.cy = 10;  
 
CPoint ptMFCBig(sHowBig); 
// or from a DWORD  
 
DWORD   dwSize;  
dwSize = MAKELONG(35, 95);
 
CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```  
  
##  <a name="offset"></a>CPoint::Offset  
 Değerleri ekler **x** ve **y** üyeleri `CPoint`.  
  
```  
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *xOffset*  
 Dengelemek için belirtir **x** üyesi `CPoint`.  
  
 *yOffset*  
 Dengelemek için belirtir **y** üyesi `CPoint`.  
  
 `point`  
 Belirtir ( [noktası](../../mfc/reference/point-structure1.md) veya `CPoint`) dengelemek için `CPoint`.  
  
 `size`  
 Belirtir ( [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) veya [CSize](../../atl-mfc-shared/reference/csize-class.md)) dengelemek için `CPoint`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]  
  
##  <a name="operator_eq_eq"></a>CPoint::operator ==  
 İki nokta arasındaki eşitlik denetler.  
  
```  
BOOL operator==(POINT point) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Puanları eşitse, sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]  
  
##  <a name="operator_neq"></a>CPoint::operator! =  
 İki nokta arasındaki eşitsizlik denetler.  
  
```  
BOOL operator!=(POINT point) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya `CPoint` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Noktaları eşit değilse sıfır olmayan; Aksi takdirde 0.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]  
  
##  <a name="operator_add_eq"></a>CPoint::operator +=  
 İlk aşırı bir boyuta ekler `CPoint`.  
  
```  
void operator+=(SIZE size) throw(); 
void operator+=(POINT point) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 İçeren bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.  
  
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci aşırı bir noktasına ekler `CPoint`.  
  
 Her iki durumda da, toplama ekleyerek yapılır **x** (veya **cx**) sağ işleneni üyesi **x** üyesi `CPoint` ve ekleyerek **y**  (veya **cy**) sağ işleneni üyesi **y** üyesi `CPoint`.  
  
 Örneğin, ekleme `CPoint(5, -7)` içeren bir değişkene `CPoint(30, 40)` değişkenine değişiklikleri `CPoint(35, 33)`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]  
  
##  <a name="operator_-_eq"></a>CPoint::operator-=  
 Sabit boyutlu bir ilk aşırı çıkarır `CPoint`.  
  
```  
void operator-=(SIZE size) throw(); 
void operator-=(POINT point) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 İçeren bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.  
  
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci aşırı bir noktasından çıkarır `CPoint`.  
  
 Her iki durumda da çıkarılmasıyla çıkarma yapılır **x** (veya **cx**) sağ işleneni üyesi **x** üyesi `CPoint` ve çıkarma**y** (veya **cy**) sağ işleneni üyesi **y** üyesi `CPoint`.  
  
 Örneğin, çıkarılmasıyla `CPoint(5, -7)` içeren bir değişkenin `CPoint(30, 40)` değişkenine değişiklikleri `CPoint(25, 47)`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]  
  
##  <a name="operator_add"></a>CPoint::operator +  
 Uzaklık için bu işleci kullanın `CPoint` tarafından bir `CPoint` veya `CSize` nesnesi veya dengelemek için bir `CRect` tarafından bir `CPoint`.  
  
```  
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `size`  
 İçeren bir [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.  
  
 `point`  
 İçeren bir [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.  
  
 `lpRect`  
 Bir işaretçi içeren bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CPoint` boyutuna göre uzaklığı bir **CPoint** noktası tarafından uzaklığı veya **CRect** noktası tarafından uzaklığı.  
  
### <a name="remarks"></a>Açıklamalar  
 Örneğin, ilk iki aşırı birini noktası dengelemek için kullanarak `CPoint(25, -19)` bir noktaya göre `CPoint(15, 5)` veya boyutu `CSize(15, 5)` değeri döndürür `CPoint(40, -14)`.  
  
 Dikdörtgen bir noktasına ekleme döndürür dikdörtgen tarafından uzaklığı sonra **x** ve **y** noktasında belirtilen değerleri. Örneğin, bir dikdörtgen dengelemek için son aşırı yüklemeleri kullanarak `CRect(125, 219, 325, 419)` bir noktaya göre `CPoint(25, -19)` döndürür `CRect(150, 200, 350, 400)`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]  
  
##  <a name="operator_-"></a>CPoint::operator-  
 İlk iki aşırı birini çıkartılacak kullanın bir `CPoint` veya `CSize` nesnesinin `CPoint`.  
  
```  
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `point`  
 A [noktası](../../mfc/reference/point-structure1.md) yapısı veya [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) nesnesi.  
  
 `size`  
 A [BOYUTU](http://msdn.microsoft.com/library/windows/desktop/dd145106) yapısı veya [CSize](../../atl-mfc-shared/reference/csize-class.md) nesnesi.  
  
 `lpRect`  
 Bir işaretçi bir [RECT](../../mfc/reference/rect-structure1.md) yapısı veya [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 A `CSize` diğer bir deyişle iki nokta arasındaki farkı bir `CPoint` bir boyutu değilleme tarafından uzaklığı bir `CRect` bir noktası değilleme tarafından uzaklığı veya `CPoint` diğer bir deyişle bir noktası değilleme.  
  
### <a name="remarks"></a>Açıklamalar  
 Üçüncü aşırı uzaklıkları bir `CRect` değilleme işlemi tarafından `CPoint`. Son olarak, negate için birli işleç kullanma `CPoint`.  
  
 Örneğin, iki nokta arasındaki farkı bulmak için ilk aşırı yüklemeleri kullanarak `CPoint(25, -19)` ve `CPoint(15, 5)` döndürür `CSize(10, -24)`.  
  
 Çıkarılmasıyla bir `CSize` gelen `CPoint` yukarıdaki gibi aynı hesaplamayı yapar ancak döndürür bir `CPoint` nesnesi değil, bir `CSize` nesnesi. Örneğin, noktası arasındaki farkı bulmak için ikinci aşırı yüklemeleri kullanarak `CPoint(25, -19)` ve boyutu `CSize(15, 5)` döndürür `CPoint(10, -24)`.  
  
 Dikdörtgen bir noktasından çıkarılmasıyla dikdörtgen uzaklık negatif tarafından döndürür **x** ve **y** noktasında belirtilen değerleri. Örneğin, dikdörtgen dengelemek için son aşırı yüklemeleri kullanarak `CRect(125, 200, 325, 400)` noktası tarafından `CPoint(25, -19)` döndürür `CRect(100, 219, 300, 419)`.  
  
 Birli işleç bir nokta negate için kullanın. Örneğin, noktasıyla birli işleç kullanılarak `CPoint(25, -19)` döndürür `CPoint(-25, 19)`.  
  
### <a name="example"></a>Örnek  
 [!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek MDI](../../visual-cpp-samples.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [POINT yapısı](../../mfc/reference/point-structure1.md)   
 [CRect sınıfı](../../atl-mfc-shared/reference/crect-class.md)   
 [CSize Sınıfı](../../atl-mfc-shared/reference/csize-class.md)



