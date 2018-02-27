---
title: "&lt;yardımcı programı&gt; işlevleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
caps.latest.revision: 
manager: ghogen
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: a442f3a4b03a62363d465107b7e2ae5f3e975249
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="ltutilitygt-functions"></a>&lt;yardımcı programı&gt; işlevleri
||||  
|-|-|-|  
|[exchange](#exchange)|[forward](#forward)|[get işlevi &lt;yardımcı programı&gt;](#get)|  
|[make_pair](#make_pair)|[move](#move)|[Değiştirme](#swap)|  
  
##  <a name="exchange"></a>  Exchange  
 **(C ++ 14)**  Bir nesne için yeni bir değer atar ve eski değerini döndürür.  
  
```cpp  
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```  
  
### <a name="parameters"></a>Parametreler  
 `val`  
 New_val değerini alacak nesne.  
  
 `new_val`  
 Değeri kopyaladığınız veya val taşındı nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 Karmaşık türler için `exchange` bir taşıma oluşturucusuna kullanılabilir, geçici bir nesne veya taşınır ve herhangi bir tür tüm kullanılabilir dönüştürme atama işleci kullanarak yeni değeri kabul eder, yeni değer kopyalama önler eski değer kopyalarken önler. Exchange işlevi farklıdır [std::swap](../standard-library/algorithm-functions.md#swap) sol bağımsız değişkeni taşımadığını veya sağ bağımsız değişkeni için kopyalanan olmasıdır.  
  
### <a name="example"></a>Örnek  
  Aşağıdaki örnekte nasıl kullanılacağını gösterir `exchange`. Gerçek Hayatta `exchange` kopyalamak pahalıdır büyük nesneler ile kullanışlıdır:  
  
```  
#include <utility>  
#include <iostream>  
  
using namespace std;  
  
struct C  
{  
int i;  
//...  
};  
int main()  
{     
// Use brace initialization   
C c1{ 1 };  
C c2{ 2 };  
C result = exchange(c1, c2);  
cout << "The old value of c1 is: " << result.i << endl;  
cout << "The new value of c1 after exchange is: " << c1.i << endl;  
  
return 0;  
}  
/* Output:  
The old value of c1 is: 1  
The new value of c1 after exchange is: 2  
*/  
```  
  
##  <a name="forward"></a>  İlet  
 Bağımsız değişken bir rvalue'da veya rvalue başvurusundaysa, bağımsız değişkenini bir rvalue başvurusuna koşullu olarak yayınlar. Bu, bir bağımsız değişkenin rvalue olma durumunu mükemmel iletim desteği sunarak iletim işlevine geri yükler.  
  
```
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Type`|Geçirilen değerin türü `Arg`, hangi olabilir türünden farklı `Arg`. Genellikle iletme işlevinin bir şablon bağımsız değişkeni tarafından belirlenir.|  
|`Arg`|Yayınlama için bağımsız değişkeni.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 Rvalue başvuru döndürür `Arg` değeri aktarılırsa `Arg` ilk olarak bir rvalue veya bir rvalue başvuru edildi; Aksi halde döndürür `Arg` türünü değiştirmeden.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırmak için bir açık şablon bağımsız değişken belirtmelisiniz `forward`.  
  
 `forward` bağımsız değişkeni iletin değil. İlk olarak bir rvalue veya rvalue başvuru ise, bunun yerine, tarafından bağımsız değişkeni bir rvalue başvuru için koşullu atama `forward` aşırı çözümlemesi bilgi iletilen bağımsız değişkeninin özgün türü ile derleyici sağlar. Bir iletme işlevi bağımsız değişken görünen türü özgün türünden farklı olabilir — örneğin, ne zaman bir rvalue bir işleve bağımsız değişken olarak kullanılan ve bir parametre adı için; bağlı bir ad sağlar, değeri gerçekte bir rvalue varolup bakılmaksızın bir lvalue — `forward` bağımsız değişkenin rvalue şahit geri yükler.  
  
 Aşırı yükleme çözünürlüğü gerçekleştirmek için bir bağımsız değişken özgün değerinin rvalue şahit geri yükleme olarak bilinir *kusursuz iletme*. Kusursuz iletme bir şablon işlevinin her iki başvuru türünün bağımsız değişkenini kabul etmesini ve aşırı yük çözümlemeleri yapılması gerektiğinde rvalue durumunu geri yüklemesini sağlar. Kusursuz iletme kullanarak, rvalues için taşıma semantiğini koruyabilir ve bağımsız değişkenlerinin yalnızca başvuru türüne göre çeşitlenen işlevler için aşırı yük sağlanmasını önleyebilirsiniz.  
  
##  <a name="get"></a>  get  
 Bir öğeyi alır bir `pair` dizin konumu veya türüne göre bir nesne.  
  
```
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
constexpr tuple_element_t<Index, pair<T1, T2>>&
get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
constexpr const tuple_element_t<Index, pair<T1, T2>>&
get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
constexpr tuple_element_t<Index, pair<T1, T2>>&&
get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
 `Index`  
 Belirtilen öğenin 0 tabanlı dizini.  
  
 `T1`  
 İlk çifti öğe türü.  
  
 `T2`  
 İkinci çifti öğesi türü.  
  
 `pr`  
 Aralarından seçim yapabileceğiniz çifti.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir öğenin bir başvuru her şablon işlevleri döndürmek kendi `pair` bağımsız değişkeni.  
  
 Dizinli aşırı yüklemeleri için değeri `Index` işlevler döndürür 0'dır `pr.first` ve değerini `Index` 1 işlevler döndürür `pr.second`. Türü `RI` döndürülen öğe türü değil.  
  
 Bir dizin parametresi olmayan aşırı yüklemeleri için tür bağımsız değişkeni tarafından döndürülecek öğenin anlaşılabilen. Çağırma `get<T>(Tuple)` derleyici hatası durumunda üretecektir `pr` t türünde bir öğe sayısından fazla veya az içerir  
  
### <a name="example"></a>Örnek  
  
```cpp  
#include <utility>  
#include <iostream>   
using namespace std;  
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index  
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)  
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;

    /*
    Output:
    9 3.14
    1 0.27
    */

}
```  
  
##  <a name="make_pair"></a>  make_pair  
 Türündeki nesneleri oluşturmak için kullanabileceğiniz bir şablon işlevi `pair`, burada parametre olarak geçirilen veri türleri temel bileşen türleri otomatik olarak seçilir.  
  
```
template <class T, class U>
pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
pair<T, U> make_pair(T&& Val1, U&& Val2);
```  
  
### <a name="parameters"></a>Parametreler  
 `Val1`  
 İlk öğesi başlatır değeri `pair`.  
  
 `Val2`  
 İkinci öğesini başlatır değeri `pair`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Oluşturulan çifti nesnesi: `pair` <  `T`, `U`> ( `Val1`, `Val2`).  
  
### <a name="remarks"></a>Açıklamalar  
 `make_pair` dönüştürür Nesne türü [reference_wrapper sınıfı](../standard-library/reference-wrapper-class.md) başvuru türleri ve diziler ve işaretçiler işlevlere küçülen dönüştürür.  
  
 Döndürülen içinde `pair` nesnesi `T` şu şekilde belirlenir:  
  
-   Giriş yazarsanız `T` olan `reference_wrapper<X>`, bir tür döndürdü `T` olan `X&`.  
  
-   Aksi takdirde, döndürülen tür `T` olan `decay<T>::type`. Varsa [decay sınıfı](../standard-library/decay-class.md) desteklenmiyor, döndürülen tür `T` giriş türü ile aynı `T`.  
  
 Döndürülen tür `U` giriş türünden benzer şekilde belirlenir `U`.  
  
 Bir avantajı `make_pair` depolanmakta nesne türlerini derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenler gibi kullanmayan `make_pair<int, int>(1, 2)` kullandığınızda `make_pair` gereksiz yere ayrıntılı olduğundan ve derleme hatasına neden olabilen karmaşık rvalue başvuru sorunlarını ekler. Bu örnekte, doğru sözdizimi olacaktır `make_pair(1, 2)`  
  
 `make_pair` Yardımcı işlevini de iki değer çifti giriş parametresi olarak gerektiren bir işlev geçirilecek mümkün kılar.  
  
### <a name="example"></a>Örnek  
  Yardımcı işlevini kullanma hakkında bir örnek `make_pair` bildirme ve bir çift başlatmak için bkz: [pair yapısı](../standard-library/pair-structure.md).  
  
##  <a name="move"></a>  Taşıma  
 Kendi bağımsız değişkenini koşulsuz olarak bir rvalue başvurusuna yayınlar ve böylece kendi türünün taşınması etkinse, taşınabileceğini belirtir.  
  
```
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`Type`|Geçirilen bağımsız değişken türünden anlaşılan bir türü `Arg`, kuralları daraltma başvurusu ile birlikte.|  
|`Arg`|Yayınlama için bağımsız değişkeni. Ancak türünü `Arg` bir rvalue başvuru belirtilmesi için görünür `move` lvalue başvuru rvalue başvuru bağlayabilirsiniz çünkü lvalue bağımsız değişkenler de kabul eder.|  
  
### <a name="return-value"></a>Dönüş Değeri  
 `Arg` bir rvalue başvuru olup olmadığına, bir başvuru türü türüdür.  
  
### <a name="remarks"></a>Açıklamalar  
 Şablon bağımsız değişken `Type` açıkça belirtilmesi, ancak geçirilen değerin türü anlaşılan amaçlanmamıştır `Arg`. Türü `Type` daha ayrıntılı kurallar daraltma başvuru göre ayarlanır.  
  
 `move` bağımsız değişkeni taşımaz. Bunun yerine, bağımsız değişkeni koşulsuz olarak atama tarafından — bir lvalue olabilir — kopyalama, geçirilen değer yerine isteğe bağlı olarak bir rvalue başvuru sonradan taşımak derleyici etkinleştirir `Arg` türü taşıma etkinse. Türü taşıma etkin değilse, bunun yerine kopyalanır.  
  
 Değer aktarılırsa `Arg` bir lvalue olan — diğer bir deyişle, bir ada sahip veya adresini alınabilir — taşıma oluştuğunda geçersiz. Geçirilen değerine karşılık gelmiyorsa `Arg` adıyla veya taşınmış sonra adresiyle tarafından.  
  
##  <a name="swap"></a>  Değiştirme  
 İki öğelerini alış verişleri [pair yapısı](../standard-library/pair-structure.md) nesneleri.  
  
```
template <class T, class U>  
void swap(pair<T, U>& left, pair<T, U>& right);
```  
  
### <a name="parameters"></a>Parametreler  
  
|Parametre|Açıklama|  
|---------------|-----------------|  
|`left`|Türünde bir nesne `pair`.|  
|`right`|Türünde bir nesne `pair`.|  
  
### <a name="remarks"></a>Açıklamalar  
 Bir avantajı `swap` depolanmakta nesne türlerini derleyici tarafından otomatik olarak belirlenir ve açıkça belirtilmesi gerekmez. Açık şablon bağımsız değişkenler gibi kullanmayan `swap<int, int>(1, 2)` kullandığınızda `swap` gereksiz yere ayrıntılı olduğundan ve derleme hatasına neden olabilen karmaşık rvalue başvuru sorunlarını ekler.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [\<yardımcı programı >](../standard-library/utility.md)



