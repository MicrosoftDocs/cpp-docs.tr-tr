---
title: "CComVariant sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
dev_langs: C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: "26"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 153c71f36eb56ce9d848b791e9a2ef16d9f6a6d0
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomvariant-class"></a>CComVariant sınıfı
Bu sınıf sarmalar `VARIANT` depolanan verilerin türünü belirten bir üye sağlama türü.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|Oluşturucu.|  
|[CComVariant:: ~ CComVariant](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|Bağlayan bir **değişken** için `CComVariant` nesnesi.|  
|[CComVariant::ChangeType](#changetype)|Dönüştürür `CComVariant` nesne için yeni bir tür.|  
|[CComVariant::Clear](#clear)|Temizler `CComVariant` nesnesi.|  
|[CComVariant::Copy](#copy)|Kopya bir **değişken** için `CComVariant` nesnesi.|  
|[CComVariant::CopyTo](#copyto)|İçeriğini kopyalar `CComVariant` nesnesi.|  
|[CComVariant::Detach](#detach)|Arka plandaki ayırır **değişken** gelen `CComVariant` nesnesi.|  
|[CComVariant::GetSize](#getsize)|İçeriği için bayt cinsinden boyutu döndüren `CComVariant` nesnesi.|  
|[CComVariant::ReadFromStream](#readfromstream)|Yükleri bir **değişken** akıştan.|  
|[CComVariant::SetByRef](#setbyref)|Başlatır `CComVariant` nesne ve ayarlar **vt** üyesine **VT_BYREF**.|  
|[CComVariant::WriteToStream](#writetostream)|Arka plandaki kaydeder **değişken** akış.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|||  
|-|-|  
|[CComVariant::operator <](#operator_lt)|Gösterir olup olmadığını `CComVariant` nesnesi, belirtilen değerinden **değişken**.|  
|[CComVariant::operator >](#operator_gt)|Gösterir olup olmadığını `CComVariant` nesnesi belirtilen büyük olan **değişken**.|  
|[operator! =](#operator_neq)|Gösterir olup olmadığını `CComVariant` nesne eşit değil belirtilen **değişken**.|  
|[işleç =](#operator_eq)|Bir değeri atar `CComVariant` nesnesi.|  
|[operator ==](#operator_eq_eq)|Gösterir olup olmadığını `CComVariant` nesne belirtilen eşittir **değişken**.|  
  
## <a name="remarks"></a>Açıklamalar  
 `CComVariant`sarmalar `VARIANT and VARIANTARG` oluşan bir birleşim ve birleşim içinde depolanan verilerin türünü belirten bir üye türü. **DEĞİŞKEN**s genellikle Otomasyon kullanılır.  
  
 `CComVariant`türetilen **değişken** , böylece yazın yerde kullanılan bir **değişken** kullanılabilir. Örneğin, kullanabilirsiniz **V_VT** türünü ayıklamak için makrosu bir `CComVariant` veya erişebilirsiniz **vt** üyesi ile doğrudan yalnızca bir **değişken**.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcomcli.h  
  
##  <a name="attach"></a>CComVariant::Attach  
 Geçerli içeriğini güvenli bir şekilde temizler `CComVariant` nesne, içeriğini kopyalar `pSrc` bu nesnesine sonra değişken türünü ayarlar `pSrc` için `VT_EMPTY`.  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSrc`  
 [in] İşaret [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) nesnesine eklenecek.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Tarafından tutulan verileri sahipliğini `pSrc` aktarılır `CComVariant` nesnesi.  
  
##  <a name="ccomvariant"></a>CComVariant::CComVariant  
 Her Oluşturucusu güvenli başlatılması işleme `CComVariant` çağırarak nesne `VariantInit` Win32 işlevi veya nesnenin değeri ve türüne göre geçirilen parametreler ayarlayarak.  
  
```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 *varSrc*  
 [in] `CComVariant` Veya `VARIANT` başlatmak için kullanılan `CComVariant` nesnesi. Kaynak değişken içeriğini hedef dönüştürme olmadan kopyalanır.  
  
 `lpszSrc`  
 [in] Başlatmak için kullanılan karakter dizesi `CComVariant` nesnesi. Sıfır sonlandırılan geniş (Unicode) karakter dizesine geçirebilirsiniz **LPCOLESTR** Oluşturucusu veya ANSI dizisi sürümü `LPCSTR` sürümü. Her iki durumda da dize bir Unicode'a dönüştürülür `BSTR` kullanılarak ayrılmış **SysAllocString**. Türü `CComVariant` nesne `VT_BSTR`.  
  
 `bSrc`  
 [in] `bool` Başlatmak için kullanılan `CComVariant` nesnesi. `bool` Bağımsız değişkeni için dönüştürülür bir **VARIANT_BOOL** depolanmakta önce. Türü `CComVariant` nesne `VT_BOOL`.  
  
 `nSrc`  
 [in] `int`, **Bayt**, **kısa**, **uzun**, **LONGLONG**, **ULONGLONG**, **kısa imzasız**, `unsigned long`, veya `unsigned int` başlatmak için kullanılan `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, veya **VT_UI4**sırasıyla.  
  
 `vtSrc`  
 [in] Değişken türü. İlk parametre olduğunda `int`, geçerli türler `VT_I4` ve **VT_INT**. İlk parametre olduğunda **uzun**, geçerli türler `VT_I4` ve `VT_ERROR`. İlk parametre olduğunda **çift**, geçerli türler `VT_R8` ve `VT_DATE`. İlk parametre olduğunda `unsigned int`, geçerli türler **VT_UI4** ve **VT_UINT**.  
  
 `fltSrc`  
 [in] **Float** başlatmak için kullanılan `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_R4`.  
  
 `dblSrc`  
 [in] **Çift** başlatmak için kullanılan `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_R8`.  
  
 `cySrc`  
 [in] **CY** başlatmak için kullanılan `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_CY`.  
  
 `pSrc`  
 [in] `IDispatch` Veya **IUnknown** başlatmak için kullanılan işaretçi `CComVariant` nesnesi. `AddRef`arabirim işaretçisi olarak adlandırılır. Türü `CComVariant` nesne **VT_DISPATCH** veya **VT_UNKNOWN**sırasıyla.  
  
 Veya, **SAFERRAY** başlatmak için kullanılan işaretçi `CComVariant` nesnesi. Bir kopyasını **SAFEARRAY** depolanan `CComVariant` nesnesi. Türü `CComVariant` nesne özgün türü bir birleşimi olacaktır **SAFEARRAY** ve **VT_ARRAY**.  
  
 `cSrc`  
 [in] `char` Başlatmak için kullanılan `CComVariant` nesnesi. Türü `CComVariant` nesne **VT_I1**.  
  
 `bstrSrc`  
 [in] BSTR başlatmak için kullanılan `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_BSTR`.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırarak temizleme yıkıcı yönetir [CComVariant::Clear](#clear).  
  
##  <a name="dtor"></a>CComVariant:: ~ CComVariant  
 Yok Edicisi.  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağrılarak temizleme yönetir [CComVariant::Clear](#clear).  
  
##  <a name="changetype"></a>CComVariant::ChangeType  
 Dönüştürür `CComVariant` nesne için yeni bir tür.  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>Parametreler  
 `vtNew`  
 [in] Yeni türü için `CComVariant` nesnesi.  
  
 `pSrc`  
 [in] Bir işaretçi `VARIANT` değeri yeni türe dönüştürülen. Varsayılan değer **NULL**seçeneğidir; yani `CComVariant` nesne yerinde dönüştürülmesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir değer geçirmek, `pSrc`, `ChangeType` bu kullanacağı **değişken** dönüştürme için kaynak olarak. Aksi takdirde `CComVariant` nesne, kaynak olacaktır.  
  
##  <a name="clear"></a>CComVariant::Clear  
 Temizler `CComVariant` çağırarak nesne `VariantClear` Win32 işlevi.  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Otomatik olarak yıkıcı çağrıları **Temizle**.  
  
##  <a name="copy"></a>CComVariant::Copy  
 Serbest bırakma `CComVariant` nesne ve belirtilen bir kopyasını atar **değişken**.  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSrc`  
 [in] Bir işaretçi [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) kopyalanacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
##  <a name="copyto"></a>CComVariant::CopyTo  
 İçeriğini kopyalar `CComVariant` nesnesi.  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>Parametreler  
 *pstrDest*  
 İşaret eden bir `BSTR` içeriğini bir kopyasını alacağı `CComVariant` nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 **CComVariant** nesne türünde olması gerekir `VT_BSTR`.  
  
##  <a name="detach"></a>CComVariant::Detach  
 Arka plandaki ayırır **değişken** gelen `CComVariant` nesne ve nesnenin türünü ayarlar `VT_EMPTY`.  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>Parametreler  
 `pDest`  
 [out] Arka plandaki döndürür `VARIANT` nesnenin değeri.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 Unutmayın, içeriğini `VARIANT` tarafından başvurulan `pDest` arama türü ve değeri atanmış önce otomatik olarak temizlenir **CComVariant** nesne.  
  
##  <a name="getsize"></a>CComVariant::GetSize  
 Basit sabit boyutu için `VARIANT`s, bu yöntem `sizeof` artı temel alınan veri türü `sizeof(VARTYPE)`.  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli içeriğinin bayt cinsinden boyutu `CComVariant` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Varsa `VARIANT` bir arabirim işaretçisi içeren `GetSize` için sorgular `IPersistStream` veya `IPersistStreamInit`. Başarılı, dönüş değeri tarafından döndürülen değerin düşük düzey 32 bit ise `GetSizeMax` artı `sizeof` bir `CLSID` ve `sizeof(VARTYPE)`. Arabirim işaretçisi ise `NULL`, `GetSize` döndürür `sizeof` bir `CLSID` artı `sizeof(VARTYPE)`. Toplam boyutu daha büyükse `ULONG_MAX`, `GetSize` döndürür `sizeof(VARTYPE)` bir hata gösterir.  
  
 Tüm diğer durumlarda, geçici bir `VARIANT` türü `VT_BSTR` geçerli yüklenen `VARIANT`. Bu uzunluğu `BSTR` boyutu dize uzunluğu artı dize uzunluğu artı artı null karakteri boyutu olarak hesaplanan `sizeof(VARTYPE)`. Varsa `VARIANT` için zorlanamaz bir `VARIANT` türü `VT_BSTR`, `GetSize` döndürür `sizeof(VARTYPE)`.  
  
 Bu yöntem tarafından döndürülen boyutu tarafından kullanılan bayt sayısıyla eşleştiğini [CComVariant::WriteToStream](#writetostream) başarılı koşullar altında.  
  
##  <a name="operator_eq"></a>CComVariant::operator =  
 Değer ve karşılık gelen tür atar `CComVariant` nesnesi.  
  
```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 *varSrc*  
 [in] `CComVariant` Veya [değişken](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) atanacak `CComVariant` nesnesi. Kaynak değişken içeriğini hedef dönüştürme olmadan kopyalanır.  
  
 `bstrSrc`  
 [in] Atanacak BSTR `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_BSTR`.  
  
 `lpszSrc`  
 [in] Atanacak karakter dizesi `CComVariant` nesnesi. Sıfır sonlandırılan geniş (Unicode) karakter dizesine geçirebilirsiniz **LPCOLESTR** işleci veya ANSI dizisi sürümü `LPCSTR` sürümü. Her iki durumda da dize bir Unicode'a dönüştürülür `BSTR` kullanılarak ayrılmış **SysAllocString**. Türü `CComVariant` nesne `VT_BSTR`.  
  
 `bSrc`  
 [in] `bool` Atanacak `CComVariant` nesnesi. `bool` Bağımsız değişkeni için dönüştürülür bir **VARIANT_BOOL** depolanmakta önce. Türü `CComVariant` nesne `VT_BOOL`.  
  
 `nSrc`  
 [in] `int`, **Bayt**, **kısa**, **uzun**, **LONGLONG**, **ULONGLONG**, **kısa imzasız**, `unsigned long`, veya `unsigned int` atanacak `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**,  **VT_UI4**, veya **VT_UI4**sırasıyla.  
  
 `fltSrc`  
 [in] **Float** atanacak `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_R4`.  
  
 `dblSrc`  
 [in] **Çift** atanacak `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_R8`.  
  
 `cySrc`  
 [in] **CY** atanacak `CComVariant` nesnesi. Türü `CComVariant` nesne `VT_CY`.  
  
 `pSrc`  
 [in] `IDispatch` Veya **IUnknown** atanacak işaretçi `CComVariant` nesnesi. `AddRef`arabirim işaretçisi olarak adlandırılır. Türü `CComVariant` nesne **VT_DISPATCH** veya **VT_UNKNOWN**sırasıyla.  
  
 Veya, bir **SAFEARRAY** atanacak işaretçi `CComVariant` nesnesi. Bir kopyasını **SAFEARRAY** depolanan `CComVariant` nesnesi. Türü `CComVariant` nesne özgün türü bir birleşimi olacaktır **SAFEARRAY** ve **VT_ARRAY**.  
  
 `cSrc`  
 [in] Atanacak char `CComVariant` nesnesi. Türü `CComVariant` nesne **VT_I1**.  
  
##  <a name="operator_eq_eq"></a>CComVariant::operator ==  
 Gösterir olup olmadığını `CComVariant` nesne belirtilen eşittir **değişken**.  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **true** , türü ve değeri *varSrc* türü ve değeri eşitse sırasıyla, `CComVariant` nesnesi. Aksi takdirde, **false**. İşleci, karşılaştırma gerçekleştirmek için kullanıcının varsayılan yerel ayar kullanır.  
  
 İşleci yalnızca VARIANT türleri değerini karşılaştırır. Dize, tamsayı ve kayan nokta ancak dizileri veya kayıtları karşılaştırır.  
  
##  <a name="operator_neq"></a>CComVariant::operator! =  
 Gösterir olup olmadığını `CComVariant` nesne eşit değil belirtilen **değişken**.  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **true** ise değer veya türü *varSrc* değeri veya türü, eşit değil sırasıyla, `CComVariant` nesne. Aksi takdirde, **false**. İşleci, karşılaştırma gerçekleştirmek için kullanıcının varsayılan yerel ayar kullanır.  
  
 İşleci yalnızca VARIANT türleri değerini karşılaştırır. Dize, tamsayı ve kayan nokta ancak dizileri veya kayıtları karşılaştırır.  
  
##  <a name="operator_lt"></a>CComVariant::operator&lt;  
 Gösterir olup olmadığını `CComVariant` nesnesi, belirtilen değerinden **değişken**.  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **true** varsa değerini `CComVariant` nesne değerini azdır *varSrc*. Aksi takdirde, **false**. İşleci, karşılaştırma gerçekleştirmek için kullanıcının varsayılan yerel ayar kullanır.  
  
##  <a name="operator_gt"></a>CComVariant::operator&gt;  
 Gösterir olup olmadığını `CComVariant` nesnesi belirtilen büyük olan **değişken**.  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **true** varsa değerini `CComVariant` nesnesidir değerinden büyük *varSrc*. Aksi takdirde, **false**. İşleci, karşılaştırma gerçekleştirmek için kullanıcının varsayılan yerel ayar kullanır.  
  
##  <a name="readfromstream"></a>CComVariant::ReadFromStream  
 Temel Ayarlar **değişken** için **değişken** belirtilen akışında yer alan.  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 [in] Bir işaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) verileri içeren akışı arabirimde.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 **ReadToStream** önceki çağrısı gerektirir [WriteToStream](#writetostream).  
  
##  <a name="setbyref"></a>CComVariant::SetByRef  
 Başlatır `CComVariant` nesne ve ayarlar **vt** üyesine **VT_BYREF**.  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `T`  
 Türü **değişken**, örneğin, `BSTR`, `int`, veya `char`.  
  
 *pT*  
 Başlatmak için kullanılan işaretçi `CComVariant` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `SetByRef`başlatır işlevi şablonudur `CComVariant` işaretçinin nesnesine *pT* ve ayarlar **vt** üyesine **VT_BYREF**. Örneğin:  
  
 [!code-cpp[NVC_ATL_Utilities#76](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>CComVariant::WriteToStream  
 Arka plandaki kaydeder **değişken** akış.  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parametreler  
 `pStream`  
 [in] Bir işaretçi [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) bir akış üzerinde arabirimi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Standart bir `HRESULT` değeri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)