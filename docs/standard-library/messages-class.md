---
title: "messages sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- xlocmes/std::messages
- xlocmes/std::messages::char_type
- xlocmes/std::messages::string_type
- xlocmes/std::messages::close
- xlocmes/std::messages::do_close
- xlocmes/std::messages::do_get
- xlocmes/std::messages::do_open
- xlocmes/std::messages::get
- xlocmes/std::messages::open
dev_langs:
- C++
helpviewer_keywords:
- std::messages [C++]
- std::messages [C++], char_type
- std::messages [C++], string_type
- std::messages [C++], close
- std::messages [C++], do_close
- std::messages [C++], do_get
- std::messages [C++], do_open
- std::messages [C++], get
- std::messages [C++], open
ms.assetid: c4c71f40-4f24-48ab-9f7c-daccd8d5bd83
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 809a5fc0a74408c484948309a62096c2e89b7af5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="messages-class"></a>messages Sınıfı
Verili bir yerel ayar için uluslararası iletilerin bir kataloğundan yerelleştirilmiş iletiler almak için bir yerel ayar olarak hizmet verebilen bir nesneyi tanımlayan bir şablon sınıfı.  
  
 Şu anda, ileti sınıfı uygulanırken bir ileti yok.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template <class CharType>  
class messages : public messages_base;
```  
  
#### <a name="parameters"></a>Parametreler  
 `CharType`  
 Bir program içindeki yerel ayarın karakterlerini kodlamak için kullanılan tür.  
  
## <a name="remarks"></a>Açıklamalar  
 Herhangi bir yerel ayar modelinde olduğu gibi, statik nesne kimliğinde depolanmış bir başlangıç sıfır değeri bulunur. Benzersiz bir pozitif değer saklı değerini erişmek için ilk deneme depolar **kimliği.**  
  
 Bu model, temelde, messages_base temel sınıfında tanımlanan iletilerin kataloğunu açar, gerekli bilgileri alır ve kataloğu kapatır.  
  
### <a name="constructors"></a>Oluşturucular  
  
|||  
|-|-|  
|[İletileri](#messages)|İleti modeli oluşturucu işlevi.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|||  
|-|-|  
|[char_type](#char_type)|İletileri görüntülemek için kullanılan bir karakter türü.|  
|[string_type](#string_type)|Türü bir dize açıklayan türü `basic_string` türü karakterler içeren `CharType`.|  
  
### <a name="member-functions"></a>Üye İşlevleri  
  
|||  
|-|-|  
|[close](#close)|İleti kataloğunu kapatır.|  
|[do_close](#do_close)|İleti kataloğunu kapatmak için çağrılan sanal işlev.|  
|[do_get](#do_get)|İleti kataloğunu almak için çağrılan sanal işlev.|  
|[do_open](#do_open)|İleti kataloğunu açmak için çağrılan sanal işlev.|  
|[get](#get)|İleti kataloğunu alır.|  
|[open](#open)|İleti kataloğunu açar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<yerel ayar >  
  
 **Namespace:** std  
  
##  <a name="char_type"></a>  messages::char_type  
 İletileri görüntülemek için kullanılan bir karakter türü.  
  
```
typedef CharType char_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon parametresi için bir eş anlamlı türüdür **CharType**.  
  
##  <a name="close"></a>  Messages::Close  
 İleti kataloğunu kapatır.  
  
```
void close(catalog _Catval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Catval`  
 Kapatılması Kataloğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlev çağrılarını [do_close](#do_close)(_ *Catval*).  
  
##  <a name="do_close"></a>  messages::do_close  
 İleti kataloğunu kapatmak için çağrılan sanal işlev.  
  
```
virtual void do_close(catalog _Catval) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Catval`  
 Kapatılması Kataloğu.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu ileti Kataloğu kapatır `_Catval`, hangi gerekir açılmıştı için önceki bir çağrı tarafından [do_open](#do_open).  
  
 *_Catval* kapalı daha önce açılmış bir kataloğundan elde edilebilir.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [kapatmak](#close), çağıran `do_close`.  
  
##  <a name="do_get"></a>  messages::do_get  
 İleti kataloğunu almak için çağrılan sanal işlev.  
  
```
virtual string_type do_get(
    catalog _Catval,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Catval`  
 Aranacak İleti katalog belirten kimlik değeri.  
  
 `_Set`  
 İlk tanımlanan bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.  
  
 `_Message`  
 İkinci tanımlanan bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.  
  
 `_Dfault`  
 Hatada döndürülen dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını döndürür `_Dfault` hatasında. Aksi halde, belirtilen ileti sırası kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu ileti Kataloğu'ndan bir ileti sırası almayı dener `_Catval`. Hale getirebilir kullanımı `_Set`, `_Message`, ve `_Dfault` böylece.  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [almak](#get), çağıran `do_get`.  
  
##  <a name="do_open"></a>  messages::do_open  
 İleti kataloğunu açmak için çağrılan sanal işlev.  
  
```
virtual catalog do_open(
    const string& _Catname,
    const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Catname`  
 Aranacak katalog adı.  
  
 `_Loc`  
 Katalogda Aranan yerel ayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Küçüktür sıfır üzerinde hatası karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki çağrı ilk bağımsız değişken olarak kullanılabilir [almak](#get).  
  
### <a name="remarks"></a>Açıklamalar  
 Korumalı üye fonksiyonu adı olan bir ileti katalog açmayı denediğinde `_Catname`. Hale getirebilir yerel kullanmak `_Loc` böylece  
  
 Dönüş değeri için bir sonraki çağrı bağımsız olarak kullanılması gereken [kapatmak](#close).  
  
### <a name="example"></a>Örnek  
  Örneğin bkz [açmak](#open), çağıran `do_open`.  
  
##  <a name="get"></a>  Messages::get  
 İleti kataloğunu alır.  
  
```
string_type get(
    catalog _CatVal,
    int _Set,
    int _Message,
    const string_type& _Dfault) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Catval`  
 Aranacak İleti katalog belirten kimlik değeri.  
  
 `_Set`  
 İlk tanımlanan bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.  
  
 `_Message`  
 İkinci tanımlanan bir ileti bir ileti Kataloğu'nda bulmak için kullanılır.  
  
 `_Dfault`  
 Hatada döndürülen dize.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir kopyasını döndürür `_Dfault` hatasında. Aksi halde, belirtilen ileti sırası kopyasını döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_get](#do_get)( `_Catval`, `_Set`, `_Message`, `_Dfault`).  
  
##  <a name="messages"></a>  Messages::Messages  
 İleti modeli oluşturucu işlevi.  
  
```
explicit messages(
    size_t _Refs = 0);

protected: messages(
    const char* _Locname,
    size_t _Refs = 0);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Refs`  
 Bellek yönetimi nesnesinin türünü belirtmek için kullanılan tamsayı değeri.  
  
 `_Locname`  
 Yerel ayar adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Olası değerler için `_Refs` parametre ve bunların anlamlı:  
  
-   0: nesne ömrü onu içeren yerel ayarları tarafından yönetilir.  
  
-   1: nesne ömrü el ile yönetilmesi gerekir.  
  
-   \> 1: Bu değerleri tanımlanmamış.  
  
 Yok Edicisi korunduğu için hiçbir doğrudan örnekler mümkündür.  
  
 Oluşturucu temel nesnesiyle başlatır **locale::**[modeli](../standard-library/locale-class.md#facet_class)( `_Refs`).  
  
##  <a name="open"></a>  Messages::Open  
 İleti kataloğunu açar.  
  
```
catalog open(
    const string& _Catname,
    const locale& _Loc) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Catname`  
 Aranacak katalog adı.  
  
 `_Loc`  
 Katalogda Aranan yerel ayar.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Küçüktür sıfır üzerinde hatası karşılaştıran bir değer döndürür. Aksi takdirde, döndürülen değer sonraki çağrı ilk bağımsız değişken olarak kullanılabilir [almak](#get).  
  
### <a name="remarks"></a>Açıklamalar  
 Üye işlevi döndürür [do_open](#do_open)( `_Catname`, `_Loc`).  
  
##  <a name="string_type"></a>  Messages::string_type  
 Türü bir dize açıklayan türü `basic_string` türü karakterler içeren **CharType**.  
  
```
typedef basic_string<CharType, Traits, Allocator> string_type;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon sınıfı uzmanlaşması türünü açıklayan [basic_string](../standard-library/basic-string-class.md) olan nesneleri ileti sıraları kopyalarını depolayabilirsiniz.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yerel ayar >](../standard-library/locale.md)   
 [messages_base sınıfı](../standard-library/messages-base-class.md)   
 [C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)



