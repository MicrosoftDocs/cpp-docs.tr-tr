---
title: CA2AEX sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CA2AEX
- ATLCONV/ATL::CA2AEX
- ATLCONV/ATL::CA2AEX::CA2AEX
- ATLCONV/ATL::CA2AEX::m_psz
- ATLCONV/ATL::CA2AEX::m_szBuffer
dev_langs:
- C++
helpviewer_keywords:
- CA2AEX class
ms.assetid: 57dc65df-d9cf-4a84-99d3-6e031dde3664
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bdbdebb1ab79ceab44a408fc182b6037f2d32fae
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="ca2aex-class"></a>CA2AEX sınıfı
Bu sınıf dize dönüştürme makroları tarafından kullanılan `CA2TEX` ve `CT2AEX`ve typedef **CA2A**.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <int t_nBufferLength = 128>
class CA2AEX
```  
  
#### <a name="parameters"></a>Parametreler  
 `t_nBufferLength`  
 Çeviri işleminde kullanılan arabellek boyutu. Varsayılan uzunluk 128 bayt'tır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2AEX::CA2AEX](#ca2aex)|Oluşturucu.|  
|[CA2AEX:: ~ CA2AEX](#dtor)|Yok Edicisi.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2AEX::operator LPSTR](#operator_lpstr)|Dönüşüm işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CA2AEX::m_psz](#m_psz)|Kaynak dizesi depolar veri üyesi.|  
|[CA2AEX::m_szBuffer](#m_szbuffer)|Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.|  
  
## <a name="remarks"></a>Açıklamalar  
 Fazladan işlevsellik gerekli olmadığı sürece kullanmak `CA2TEX`, `CT2AEX`, veya **CA2A** kendi kodu.  
  
 Bu sınıf dönüştürme işleminin sonucu depolamak için kullanılan bir sabit boyutlu statik arabellek içerir. Bellek kullanarak sınıfı sonucu statik belleğe sığmayacak kadar büyük olursa ayırır `malloc`, nesne kapsam dışına çıktığında bellek boşaltma. Bu, metin dönüşüm makroları önceki sürümlerinde ATL, bu sınıfın Döngülerde kullanmak güvenli ve yığın taşması olmaz sağlar.  
  
 Sınıf başarısız olur ve yığın bellek çalışırsa, çağrı `AtlThrow` bağımsız değişkeni ile **E_OUTOFMEMORY**.  
  
 Varsayılan olarak, ATL dönüştürme sınıfları ve makroları geçerli iş parçacığının ANSI kod sayfası dönüştürme için kullanın.  
  
 Aşağıdaki makroları bu sınıfa bağlıdır:  
  
- `CA2TEX`  
  
- `CT2AEX`  
  
 Aşağıdaki typedef bu sınıfa bağlıdır:  
  
- **CA2A**  
  
 Bu metin dönüşüm makroları tartışma için bkz [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md).  
  
## <a name="example"></a>Örnek  
 Bkz: [ATL ve MFC dize dönüştürme makrolarını](string-conversion-macros.md) Bu dize dönüştürme makrolarını kullanma örneği için.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlconv.h  
  
##  <a name="ca2aex"></a>  CA2AEX::CA2AEX  
 Oluşturucu.  
  
```
CA2AEX(LPCSTR psz, UINT nCodePage) throw(...);
CA2AEX(LPCSTR psz) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `psz`  
 Dönüştürülecek metin dizesi.  
  
 `nCodePage`  
 Bu sınıftaki kullanılmayan.  
  
### <a name="remarks"></a>Açıklamalar  
 Çeviri için gerekli olan arabellek oluşturur.  
  
##  <a name="dtor"></a>  CA2AEX:: ~ CA2AEX  
 Yok Edicisi.  
  
```
~CA2AEX() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Ayrılmış arabelleğe boşaltır.  
  
##  <a name="m_psz"></a>  CA2AEX::m_psz  
 Kaynak dizesi depolar veri üyesi.  
  
```
LPSTR m_psz;
```  
  
##  <a name="m_szbuffer"></a>  CA2AEX::m_szBuffer  
 Dönüştürülmüş dizeyi depolamak için kullanılan statik arabelleği.  
  
```
char m_szBuffer[ t_nBufferLength];
```  
  
##  <a name="operator_lpstr"></a>  CA2AEX::operator LPSTR  
 Dönüşüm işleci.  
  
```
operator LPSTR() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Metin dizesini türü olarak döndürür **LPSTR**.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CA2CAEX sınıfı](../../atl/reference/ca2caex-class.md)   
 [CA2WEX sınıfı](../../atl/reference/ca2wex-class.md)   
 [CW2AEX sınıfı](../../atl/reference/cw2aex-class.md)   
 [CW2CWEX sınıfı](../../atl/reference/cw2cwex-class.md)   
 [CW2WEX sınıfı](../../atl/reference/cw2wex-class.md)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)