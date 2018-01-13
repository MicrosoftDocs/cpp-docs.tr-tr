---
title: "CW2WEX sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CW2WEX
- ATLCONV/ATL::CW2WEX
- ATLCONV/ATL::CW2WEX::CW2WEX
- ATLCONV/ATL::CW2WEX::m_psz
- ATLCONV/ATL::CW2WEX::m_szBuffer
dev_langs: C++
helpviewer_keywords: CW2WEX class
ms.assetid: 46262e56-e0d2-41fe-855b-0b67ecc8fcd7
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c35439b1309e75359177cf45ade4c6be9459f623
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cw2wex-class"></a>CW2WEX sınıfı
Bu sınıf dize dönüştürme makroları tarafından kullanılan `CW2TEX` ve `CT2WEX`ve typedef `CW2W`.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <int t_nBufferLength = 128>  
class CW2WEX
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_nBufferLength`  
 Çeviri işleminde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2WEX::CW2WEX](#cw2wex)|Oluşturucu.|  
|[CW2WEX:: ~ CW2WEX](#dtor)|Yok Edicisi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2WEX::operator LPWSTR](#operator_lpwstr)|Dönüşüm işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CW2WEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
|[CW2WEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Fazladan işlevsellik gerekli olmadığı sürece kullanmak `CW2TEX`, `CT2WEX`, veya `CW2W` kodunuzda.  
  
 Bu sınıf dönüştürme işleminin sonucu depolamak için kullanılan bir sabit boyutlu statik arabellek içerir. Bellek kullanarak sınıfı sonucu statik belleğe sığmayacak kadar büyük olursa ayırır `malloc`, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıfın Döngülerde kullanmak güvenli ve yığın taşması olmaz sağlar.  
  
 Sınıf başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` bağımsız değişkeni ile **E_OUTOFMEMORY**.  
  
 Varsayılan olarak, ATL dönüştürme sınıfları ve makroları geçerli iş parçacığının ANSI kod sayfası dönüştürme için kullanın.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- `CW2TEX`  
  
- `CT2WEX`  
  
 Aşağıdaki typedef bu sınıfa bağlıdır:  
  
- `CW2W`  
  
 Bu metin dönüşüm makroları tartışma için bkz [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="cw2wex"></a>CW2WEX::CW2WEX  
 Oluşturucu.  
  
```
CW2WEX(LPCWSTR psz, UINT nCodePage) throw(...);
CW2WEX( LPCWSTR  psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Dönüştürülecek metin dizesi.  
  
 `nCodePage`  
 Kod sayfası. Bu sınıf kullanılmaz.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri için gerekli olan arabellek oluşturur.  
  
##  <a name="dtor"></a>CW2WEX:: ~ CW2WEX  
 Yok Edicisi...  
  
```
~CW2WEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış arabelleğe boşaltır.  
  
##  <a name="m_psz"></a>CW2WEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPWSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>CW2WEX::m_szBuffer  
 Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.  
  
```
wchar_t m_szBuffer[t_nBufferLength];
```  
  
##  <a name="operator_lpwstr"></a>CW2WEX::operator LPWSTR  
 Atama işleci.  
  
```  
operator LPWSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesini türü olarak döndürür `LPWSTR`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2AEX sınıfı](../../atl/reference/ca2aex-class.md)   
 [CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)
