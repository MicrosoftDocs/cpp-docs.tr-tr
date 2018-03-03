---
title: "CSpinButtonCtrl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::CSpinButtonCtrl
- AFXCMN/CSpinButtonCtrl::Create
- AFXCMN/CSpinButtonCtrl::CreateEx
- AFXCMN/CSpinButtonCtrl::GetAccel
- AFXCMN/CSpinButtonCtrl::GetBase
- AFXCMN/CSpinButtonCtrl::GetBuddy
- AFXCMN/CSpinButtonCtrl::GetPos
- AFXCMN/CSpinButtonCtrl::GetRange
- AFXCMN/CSpinButtonCtrl::SetAccel
- AFXCMN/CSpinButtonCtrl::SetBase
- AFXCMN/CSpinButtonCtrl::SetBuddy
- AFXCMN/CSpinButtonCtrl::SetPos
- AFXCMN/CSpinButtonCtrl::SetRange
dev_langs:
- C++
helpviewer_keywords:
- CSpinButtonCtrl [MFC], CSpinButtonCtrl
- CSpinButtonCtrl [MFC], Create
- CSpinButtonCtrl [MFC], CreateEx
- CSpinButtonCtrl [MFC], GetAccel
- CSpinButtonCtrl [MFC], GetBase
- CSpinButtonCtrl [MFC], GetBuddy
- CSpinButtonCtrl [MFC], GetPos
- CSpinButtonCtrl [MFC], GetRange
- CSpinButtonCtrl [MFC], SetAccel
- CSpinButtonCtrl [MFC], SetBase
- CSpinButtonCtrl [MFC], SetBuddy
- CSpinButtonCtrl [MFC], SetPos
- CSpinButtonCtrl [MFC], SetRange
ms.assetid: 509bfd76-1c5a-4af6-973f-e133c0b87734
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1b00fc554c6ca677756cf6a9a9c7fa83cd9d255f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cspinbuttonctrl-class"></a>CSpinButtonCtrl sınıfı
Windows ortak değer değiştirme düğmesi denetimi işlevselliğini sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class CSpinButtonCtrl : public CWnd  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSpinButtonCtrl::CSpinButtonCtrl](#cspinbuttonctrl)|Oluşturan bir `CSpinButtonCtrl` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CSpinButtonCtrl::Create](#create)|Değer değiştirme düğmesi denetimi oluşturur ve ona ekler bir `CSpinButtonCtrl` nesnesi.|  
|[CSpinButtonCtrl::CreateEx](#createex)|Değer değiştirme düğmesi denetimi belirtilen Windows genişletilmiş stilleri oluşturur ve ekler bir `CSpinButtonCtrl` nesnesi.|  
|[CSpinButtonCtrl::GetAccel](#getaccel)|Değer değiştirme düğmesi denetimi için hızlandırma bilgilerini alır.|  
|[CSpinButtonCtrl::GetBase](#getbase)|Değer değiştirme düğmesi denetimi için geçerli temel alır.|  
|[CSpinButtonCtrl::GetBuddy](#getbuddy)|Geçerli arkadaş penceresi için bir işaretçi alır.|  
|[CSpinButtonCtrl::GetPos](#getpos)|Değer değiştirme düğmesi denetimi geçerli konumunu alır.|  
|[CSpinButtonCtrl::GetRange](#getrange)|Üst ve alt sınırları (aralık) için bir değer değiştirme düğmesi denetimi alır.|  
|[CSpinButtonCtrl::SetAccel](#setaccel)|Değer değiştirme düğmesi denetimi hızlandırma ayarlar.|  
|[CSpinButtonCtrl::SetBase](#setbase)|Değer değiştirme düğmesi denetimi için temel ayarlar.|  
|[CSpinButtonCtrl::SetBuddy](#setbuddy)|Arkadaş pencerenin değer değiştirme düğmesi denetimi için ayarlar.|  
|[CSpinButtonCtrl::SetPos](#setpos)|Geçerli konumu denetimi için ayarlar.|  
|[CSpinButtonCtrl::SetRange](#setrange)|Üst ve alt sınırları (aralık) bir değer değiştirme düğmesi denetimi için ayarlar.|  
  
## <a name="remarks"></a>Açıklamalar  
 "(Bir yukarı-aşağı denetimi olarak da bilinir) bir değer değiştirme düğmesi denetimi", kullanıcının artırın veya kaydırma konumunu veya Yardımcısı denetiminde gösterilen sayı gibi bir değer azaltma için tıklatabileceği ok düğmelerini çiftidir. Değer değiştirme düğmesi denetimi ile ilişkilendirilen değeri, geçerli konumuna adı verilir. Değer değiştirme düğmesi denetimi "arkadaş pencere." olarak adlandırılan bir yardımcı denetimle en sık kullanılan  
  
 Bu denetim (ve bu nedenle `CSpinButtonCtrl` sınıfı) yalnızca Windows 95/98 ve Windows NT sürüm 3.51 altında çalışan programları için kullanılabilir ve üzerinde desteklenir.  
  
 Kullanıcı için bir değer değiştirme düğmesi denetimi ve arkadaş penceresini genellikle gibi tek bir denetim arayın. Değer değiştirme düğmesi denetimi otomatik olarak kendisini yanındaki kendi arkadaş penceresi, konum olduğunu ve geçerli konumuna arkadaş penceresinin başlık otomatik olarak ayarlayın, belirtebilirsiniz. Sayısal giriş kullanıcıdan istemek için bir düzen denetimi ile değer değiştirme düğmesi denetimi kullanın.  
  
 Yukarı Ok tıklatarak en doğru geçerli konumu, ve aşağı oka tıklayarak geçerli konumu en düşük doğru taşır. Varsayılan olarak, en az 100'dür ve en fazla 0'dır. En düşük ayarı (örneğin, varsayılan ayarlar kullanıldığında) ayarlama, Yukarı Ok düşüşleri tıklatarak üst sınırdan büyük olduğundan zaman konum değerini ve aşağı oka tıklayarak artırır.  
  
 Değer değiştirme düğmesi denetimi bir arkadaş penceresi olmadan Basitleştirilmiş kaydırma çubuğunun sıralama çalışır. Örneğin, bir sekme denetimi, kullanıcı tarafından ek sekmeler görünüme gidin sağlamak için bir değer değiştirme düğmesi denetimi görüntüler.  
  
 Kullanma hakkında daha fazla bilgi için `CSpinButtonCtrl`, bkz: [denetimleri](../../mfc/controls-mfc.md) ve [kullanarak CSpinButtonCtrl](../../mfc/using-cspinbuttonctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSpinButtonCtrl`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** afxcmn.h  
  
##  <a name="create"></a>CSpinButtonCtrl::Create  
 Değer değiştirme düğmesi denetimi oluşturur ve ona ekler bir `CSpinButtonCtrl` nesnesi...  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwStyle`  
 Değer değiştirme düğmesi denetimi 's stilini belirtir. Değer değiştirme düğmesi denetimi stilleri herhangi bir bileşimini denetime uygulayın. Bu stiller açıklanan [yukarı-aşağı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb759885) Windows SDK.  
  
 `rect`  
 Değer değiştirme düğmesi denetimin boyutunu ve konumunu belirtir. Ya da olabilir bir [CRect](../../atl-mfc-shared/reference/crect-class.md) nesnesi veya bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) yapısı  
  
 `pParentWnd`  
 Değer değiştirme düğmesi denetimi ait ana penceresinde, genellikle bir işaretçi bir `CDialog`. Değil olmalıdır **NULL.**  
  
 `nID`  
 Değer değiştirme düğmesi denetimi kişinin kimliğini belirtir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başlatma başarılı olduğunda sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Oluşturmak bir `CSpinButtonCtrl` iki adımda ilk nesne, Oluşturucusu arayın ve ardından çağrısı **oluşturma**, değer değiştirme düğmesi denetimi oluşturur ve ekler `CSpinButtonCtrl` nesnesi.  
  
 Değer değiştirme düğmesi denetimi ile genişletilmiş pencere stilleri oluşturmak için arama [CSpinButtonCtrl::CreateEx](#createex) yerine **oluşturma**.  
  
##  <a name="createex"></a>CSpinButtonCtrl::CreateEx  
 Bir denetimi (alt pencere) oluşturur ve bunu ile ilişkilendirir `CSpinButtonCtrl` nesnesi.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Parametreler  
 `dwExStyle`  
 Oluşturulan denetim genişletilmiş stilini belirtir. Genişletilmiş windows stilleri listesi için bkz: `dwExStyle` parametresi için [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows SDK'sındaki.  
  
 `dwStyle`  
 Değer değiştirme düğmesi denetimi 's stilini belirtir. Değer değiştirme düğmesi denetimi stilleri herhangi bir bileşimini denetime uygulayın. Bu stiller açıklanan [yukarı-aşağı denetim stilleri](http://msdn.microsoft.com/library/windows/desktop/bb759885) Windows SDK.  
  
 `rect`  
 Bir başvuru bir [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) boyutunu ve konumunu, istemci koordinatları oluşturulacak penceresinin açıklayan yapısı `pParentWnd`.  
  
 `pParentWnd`  
 Denetimin üst penceresi için bir işaretçi.  
  
 `nID`  
 Denetimin alt pencere kimliği  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `CreateEx` yerine [oluşturma](#create) Windows genişletilmiş stili önsöz tarafından belirtilen Genişletilmiş Windows stillerini uygulamak için **WS_EX_**.  
  
##  <a name="cspinbuttonctrl"></a>CSpinButtonCtrl::CSpinButtonCtrl  
 Oluşturan bir `CSpinButtonCtrl` nesnesi.  
  
```  
CSpinButtonCtrl();
```  
  
##  <a name="getaccel"></a>CSpinButtonCtrl::GetAccel  
 Değer değiştirme düğmesi denetimi için hızlandırma bilgilerini alır.  
  
```  
UINT GetAccel(
    int nAccel,  
    UDACCEL* pAccel) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 `nAccel`  
 Tarafından belirtilen dizisindeki öğelerin sayısı `pAccel`.  
  
 `pAccel`  
 Bir dizi işaretçi [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) yapıları hızlandırma bilgilerini alır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Hızlandırıcı yapılarının sayısı aldı.  
  
##  <a name="getbase"></a>CSpinButtonCtrl::GetBase  
 Değer değiştirme düğmesi denetimi için geçerli temel alır.  
  
```  
UINT GetBase() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli taban değeri.  
  
##  <a name="getbuddy"></a>CSpinButtonCtrl::GetBuddy  
 Geçerli arkadaş penceresi için bir işaretçi alır.  
  
```  
CWnd* GetBuddy() const;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli arkadaş penceresi için bir işaretçi.  
  
##  <a name="getpos"></a>CSpinButtonCtrl::GetPos  
 Değer değiştirme düğmesi denetimi geçerli konumunu alır.  
  
```  
int GetPos() const;  int GetPos32(LPBOOL lpbError = NULL) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *lpbError*  
 Başarıyla alındı veya sıfır olmayan bir hata oluşursa gösteren bir işaretçidir sıfır ise ayarlanan değer bir Boole değeri. Bu parametre ayarlanmışsa **NULL**, hataları bildirilmedi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm düşük düzey Word'de 16 bit geçerli konumunu döndürür. Yüksek düzey bir hata oluştuysa sıfır olmayan bir sözcüktür.  
  
 İkinci sürümü 32-bit konumunu döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürülen değer işlediğinde, Denetim arkadaş penceresinin açıklamalı alt yazı göre geçerli konumunu güncelleştirir. Denetimi arkadaş pencere ise veya geçersiz veya aralık dışı bir değer resim yazısını belirtir, bir hata döndürür.  
  
##  <a name="getrange"></a>CSpinButtonCtrl::GetRange  
 Üst ve alt sınırları (aralık) için bir değer değiştirme düğmesi denetimi alır.  
  
```  
DWORD GetRange() const;  
  
void GetRange(
    int& lower,  
    int& upper) const;  
  
void GetRange32(
    int& lower,  
    int &upper) const;  
```  
  
### <a name="parameters"></a>Parametreler  
 *daha düşük*  
 Denetim için alt sınır alan tamsayı başvuru.  
  
 *üst*  
 Denetim için üst sınırı alır tamsayı başvuru.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İlk sürüm üst ve alt sınırları içeren bir 32 bit değeri döndürür. Düşük düzey word denetimi için üst sınır ve yüksek düzey word alt sınırı.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini `GetRange32` değer değiştirme düğmesi denetimi 's Aralık 32 bitlik bir tamsayı olarak alır.  
  
##  <a name="setaccel"></a>CSpinButtonCtrl::SetAccel  
 Değer değiştirme düğmesi denetimi hızlandırma ayarlar.  
  
```  
BOOL SetAccel(
    int nAccel,  
    UDACCEL* pAccel);
```  
  
### <a name="parameters"></a>Parametreler  
 `nAccel`  
 Sayısı [UDACCEL](http://msdn.microsoft.com/library/windows/desktop/bb759897) tarafından belirtilen yapıları `pAccel`.  
  
 `pAccel`  
 Bir dizi işaretçi `UDACCEL` hızlandırma bilgiler içeren yapıları. Öğeleri göre artan sırada sıralanması **nSec** üyesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılıysa sıfır olmayan; Aksi takdirde 0.  
  
##  <a name="setbase"></a>CSpinButtonCtrl::SetBase  
 Değer değiştirme düğmesi denetimi için temel ayarlar.  
  
```  
int SetBase(int nBase);
```  
  
### <a name="parameters"></a>Parametreler  
 `nBase`  
 Denetim için yeni taban değeri. Ondalık için 10 veya 16 onaltılık için olabilir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki taban değeri başarılı olursa, ya da geçersiz bir taban verilirse, sıfır.  
  
### <a name="remarks"></a>Açıklamalar  
 Taban değeri arkadaş penceresinin sayıları ondalık ya da onaltılık basamak görüntülenip görüntülenmeyeceğini belirler. Onaltılık sayı her zaman imzasız; ondalık sayılar oturum açtınız.  
  
##  <a name="setbuddy"></a>CSpinButtonCtrl::SetBuddy  
 Arkadaş pencerenin değer değiştirme düğmesi denetimi için ayarlar.  
  
```  
CWnd* SetBuddy(CWnd* pWndBuddy);
```  
  
### <a name="parameters"></a>Parametreler  
 `pWndBuddy`  
 Yeni bir arkadaş penceresi işaretçi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki arkadaş penceresi için bir işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürme denetimi neredeyse her zaman bazı içerikler görüntüleyen bir düzenleme denetimi gibi başka bir pencere ile ilişkilidir. Bu diğer Pencere döndürme denetimi "arkadaş" adı verilir.  
  
##  <a name="setpos"></a>CSpinButtonCtrl::SetPos  
 Değer değiştirme düğmesi denetimi geçerli konumunu ayarlar.  
  
```  
int SetPos(int nPos);  
int SetPos32(int nPos);
```  
  
### <a name="parameters"></a>Parametreler  
 `nPos`  
 Yeni konumu denetimi için. Bu değer, denetim için üst ve alt sınırları tarafından belirtilen aralıkta olmalıdır.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önceki konumdan (16 bit duyarlık `SetPos`, 32 bit için precision `SetPos32`).  
  
### <a name="remarks"></a>Açıklamalar  
 `SetPos32`32-bit konumunu ayarlar.  
  
##  <a name="setrange"></a>CSpinButtonCtrl::SetRange  
 Üst ve alt sınırları (aralık) bir değer değiştirme düğmesi denetimi için ayarlar.  
  
```  
void SetRange(
    short nLower,  
    short nUpper);

 
void SetRange32(
    int nLower,  
    int nUpper);
```  
  
### <a name="parameters"></a>Parametreler  
 `nLower`ve`nUpper`  
 Denetim için üst ve alt sınırları. İçin `SetRange`, hiçbiri sınırı büyük olamayacağı **UD_MAXVAL** veya küçüktür **UD_MINVAL**; Ayrıca, iki sınır arasındaki farkı aşamaz **UD_MAXVAL**. `SetRange32`herhangi bir kısıtlama sınırları yerleştirir; Tüm tamsayılar kullanın.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevini `SetRange32` 32-bit aralığı değer değiştirme düğmesi denetimi için ayarlar.  
  
> [!NOTE]
>  Değer değiştirme düğmesi için varsayılan aralığı sıfır (0) olarak ayarlanmış maksimum ve 100'e ayarlayın minimum yok. En büyük değer en küçük değerden daha küçük olduğundan yukarı oka tıklayarak konumu düşürür ve aşağı oka tıklayarak onu artmasına neden olur. Kullanım `CSpinButtonCtrl::SetRange` bu değerleri ayarlamak için.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [MFC örnek CMNCTRL2](../../visual-cpp-samples.md)   
 [CWnd sınıfı](../../mfc/reference/cwnd-class.md)   
 [Hiyerarşi grafiği](../../mfc/hierarchy-chart.md)   
 [CSliderCtrl Sınıfı](../../mfc/reference/csliderctrl-class.md)
