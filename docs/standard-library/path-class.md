---
title: "PATH sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: filesystem/std::experimental::filesystem::path
dev_langs: C++
ms.assetid: 8a1227ca-aeb2-4e0e-84aa-86e34e4f4fe8
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4221702df42bc82d1a0573f9a8b10252017b282a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="path-class"></a>path Sınıfı
**Yolu** sınıfı dize türünde bir nesne depolar\_exposition, uygun bir yol adı olarak kullanılması amacıyla burada myname adlı türü. dize\_türüdür basic eşanlamlısı\_dize\<value_type >, burada değer\_Windows altında char veya wchar_t POSIX altında eşanlamlısı türüdür.  
  
 Daha fazla bilgi ve kod örnekleri için bkz: [dosya sistemi Gezinti (C++)](../standard-library/file-system-navigation.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
class path;  
```  
  
## <a name="pathappend"></a>PATH::Append  
  
```cpp  
template <class Source>  
path& append(const Source& source);  
   
template <class InIt>  
path& append(InIt first, InIt last);
```  
  
 Üye işlevleri dönüştürülür ve gerektiğinde preferred_separator ekleme YOLUM için belirtilen sırası ekleyin.  
  
## <a name="pathassign"></a>PATH::Assign  
  
```cpp  
template <class Source>  
path& assign(const Source& source);  
  
template <class InIt>  
path& assign(InIt first, InIt last);
```  
  
 Üye işlevleri YOLUM gerektiği şekilde dönüştürülmüş belirtilen dizisi ile değiştirin.  
  
## <a name="pathbegin"></a>PATH::Begin  
  
```cpp  
iterator begin() const;
```  
  
 İlk yol öğe pathname belirleme path::iterator varsa döndürür.  
  
## <a name="pathcstr"></a>PATH::c_str  
  
```cpp  
const value_type& *c_str() const noexcept;  
```  
  
 Bir işaretçi YOLUM ilk karakteri döndürür.  
  
## <a name="pathclear"></a>PATH::Clear  
  
```cpp  
void clear() noexcept;  
```  
  
 Üye işlevini mypath.clear() yürütür  
  
## <a name="pathcompare"></a>PATH::COMPARE  
  
```cpp  
int compare(const path& pval) const noexcept;  
int compare(const string_type& str) const;
int compare(const value_type *ptr) const;
```  
  
 İlk işlev mypath.compare(pval.native()) döndürür. İkinci işlev mypath.compare(str) döndürür. Üçüncü işlevi mypath.compare(ptr) döndürür.  
  
## <a name="pathconcat"></a>PATH::concat  
  
```cpp  
template <class Source>  
path& concat(const Source& source);  
  
template <class InIt>  
path& concat(InIt first, InIt last);
```  
  
 Üye işlevleri dönüştürülen YOLUM (ancak bir ayırıcı ekleme değil) belirtilen sırası sona gerektiğinde.  
  
## <a name="pathconstiterator"></a>PATH::const_iterator  
  
```cpp  
typedef iterator const_iterator;  
```  
  
 Yineleyici eşanlamlısı türüdür.  
  
## <a name="pathempty"></a>PATH::empty  
  
```cpp  
bool empty() const noexcept;  
```  
  
 MYPATH.Empty() döndürür.  
  
## <a name="pathend"></a>PATH::End  
  
```cpp  
iterator end() const;
```  
  
 Bitiş dizisi yineleyici türü yineleyici birini döndürür.  
  
## <a name="pathextension"></a>PATH::Extension  
  
```cpp  
path extension() const;
```  
  
 Filename() X soneki döndürür şekilde:  
  
 X path(".") &#124; &#124; == X path("..") == ya da X hiçbir nokta içeriyorsa, sonek boştur.  
  
 Aksi takdirde soneki ile başlayan (ve içerir) en sağdaki nokta.  
  
## <a name="pathfilename"></a>PATH::filename  
  
```cpp  
path filename() const;
```  
  
 Kök dizin bileşenini myname, özellikle döndürür `empty()  path() : *--end()`. Bileşen boş olabilir.  
  
## <a name="pathgenericstring"></a>PATH::generic_string  
  
```cpp  
template <class Elem,  
    class Traits = char_traits<Elem>,  
    class Alloc = allocator<Elem>>  
  basic_string<Elem, Traits, Alloc>  
    generic_string(const Alloc& al = Alloc()) const;
  
string generic_string() const;
```  
  
 Döndürür `this->string<Elem, Traits, Alloc>(al)` ile (Windows altında) bir ters eğik çizgi bir eğik dönüştürülür.  
  
## <a name="pathgenericu16string"></a>PATH::generic_u16string  
  
```cpp  
u16string generic_u16string() const;
```  
  
 Tüm ters eğik çizgi ile u16string() (Windows altında) döndürür bir eğik dönüştürülür.  
  
## <a name="pathgenericu32string"></a>PATH::generic_u32string  
  
```cpp  
u32string generic_u32string() const;
```  
  
 Tüm ters eğik çizgi ile u32string() (Windows altında) döndürür bir eğik dönüştürülür.  
  
## <a name="pathgenericu8string"></a>PATH::generic_u8string  
  
```cpp  
string generic_u8string() const;
```  
  
 Tüm ters eğik çizgi ile u8string() (Windows altında) döndürür bir eğik dönüştürülür.  
  
## <a name="pathgenericwstring"></a>PATH::generic_wstring  
  
```cpp  
wstring generic_wstring() const;
```  
  
 Tüm ters eğik çizgi ile wstring() (Windows altında) döndürür bir eğik dönüştürülür.  
  
## <a name="pathhasextension"></a>PATH::has_extension  
  
```cpp  
bool has_extension() const;
```  
  
 Verir! extension().empty().  
  
## <a name="pathhasfilename"></a>PATH::has_filename  
  
```cpp  
bool has_filename() const;
```  
  
 Verir! filename().empty().  
  
## <a name="pathhasparentpath"></a>PATH::has_parent_path  
  
```cpp  
bool has_parent_path() const;
```  
  
 Verir! parent_path().empty().  
  
## <a name="pathhasrelativepath"></a>PATH::has_relative_path  
  
```cpp  
bool has_relative_path() const;
```  
  
 Verir! relative_path().empty().  
  
## <a name="pathhasrootdirectory"></a>PATH::has_root_directory  
  
```cpp  
bool has_root_directory() const;
```  
  
 Verir! root_directory().empty().  
  
## <a name="pathhasrootname"></a>PATH::has_root_name  
  
```cpp  
bool has_root_name() const;
```  
  
 Verir! root_name().empty().  
  
## <a name="pathhasrootpath"></a>PATH::has_root_path  
  
```cpp  
bool has_root_path() const;
```  
  
 Verir! root_path().empty().  
  
## <a name="pathhasstem"></a>PATH::has_stem  
  
```cpp  
bool has_stem() const;
```  
  
 Verir! stem().empty().  
  
## <a name="pathisabsolute"></a>PATH::is_absolute  
  
```cpp  
bool is_absolute() const;
```  
  
 Windows için işlevi has_root_name() döndürür & & has_root_directory(). POSIX için has_root_directory() işlevi döndürür.  
  
## <a name="pathisrelative"></a>PATH::is_relative  
  
```cpp  
bool is_relative() const;
```  
  
 Verir! is_absolute().  
  
## <a name="pathiterator"></a>PATH::iterator  
  
```cpp  
class iterator  
   {
   // bidirectional iterator for path  
   typedef bidirectional_iterator_tag iterator_category;  
   typedef path_type value_type;  
   typedef ptrdiff_t difference_type;  
   typedef const value_type *pointer;  
   typedef const value_type& reference;  
   // ...  
   };  
```  
  
 Sınıf sırada myname yolu bileşenlerinin atar çift yönlü sabit yineleyici açıklanmaktadır:  
  
1.  kök adı, mevcutsa  
  
2.  varsa, kök dizini  
  
3.  varsa dosya ile biten üst yolu, varsa, kalan dizin öğeleri    
  
 Pval tür yolu, bir nesne için:  
  
1.  PATH::iterator X = pval.begin() varsa pathname ilk yol öğe belirler.  
  
2.  X == X noktaları bileşenlerinin zaman dizinin sonuna yalnızca geçmiş pval.end() doğrudur.  
  
3. * X geçerli bileşenin eşleşen bir dize döndürür.  
  
4.  ++ X dizisinin sonraki bileşen varsa belirler.  
  
5.  --X sırası önceki bileşeni varsa belirler.  
  
6.  Myname değiştirilmesine myname öğelerinde belirleme tüm yineleyiciler geçersiz kılar.  
  
## <a name="pathmakepreferred"></a>PATH::make_preferred  
  
```cpp  
path& make_preferred();
```  
  
 Üye işlevini her ayırıcı preferred_separator için gerektiği şekilde dönüştürür.  
  
## <a name="pathnative"></a>PATH::Native  
  
```cpp  
const string_type& native() const noexcept;  
```  
  
 Myname döndürür.  
  
## <a name="pathoperator"></a>PATH::operator =  
  
```cpp  
path& operator=(const path& right);
path& operator=(path&& right) noexcept;  
  
template <class Source>  
path& operator=(const Source& source);
```  
  
 İlk üye işleci için myname right.myname kopyalar. İkinci üye işleci için myname right.myname taşır. Üçüncü üye işleci aynı şekilde davranır * bu path(source) =.  
  
## <a name="pathoperator"></a>PATH::operator +=  
  
```cpp  
path& operator+=(const path& right);
path& operator+=(const string_type& str);
path& operator+=(const value_type *ptr);
path& operator+=(value_type elem);
  
template <class Source>  
path& operator+=(const Source& source);
  
template <class Elem>  
path& operator+=(Elem elem);
```  
  
 Üye işlevleri aşağıdaki karşılık gelen ifadeler ile aynı şekilde davranır:  
  
1.  concat(right);  
  
2.  concat(Path(str));  
  
3.  concat(PTR);  
  
4.  concat (STRING_TYPE (1, elem));  
  
5.  concat(Source);  
  
6.  concat (yolu (basic_string\<Elem >(1, elem)));  
  
## <a name="pathoperator"></a>PATH::operator / =  
  
```cpp  
path& operator/=(const path& right);  
  
template <class Source>  
path& operator/=(const Source& source);
```  
  
 Üye işlevleri aşağıdaki karşılık gelen ifadeler ile aynı şekilde davranır:  
  
1.  Append(right);  
  
2.  Append(Source);  
  
## <a name="pathoperator-stringtype"></a>PATH::operator STRING_TYPE  
  
```cpp  
operator string_type() const;
```  
  
 Üye işleci myname döndürür.  
  
## <a name="pathparentpath"></a>PATH::parent_path  
  
```cpp  
path parent_path() const;
```  
  
 Üst myname, özellikle filename().native() ve hemen önceki dizin ayırıcı kaldırdıktan sonra myname önek yol bileşenini döndürür. (Eşit, varsa begin()! end(), = [begin(), / = işleci sırayla uygulayarak--end()). aralığında tüm öğeleri birleştirme olduğu) Bileşen boş olabilir.  
  
## <a name="pathpath"></a>PATH::PATH  
  
```cpp  
path();

path(const path& right);
path(path&& right) noexcept;  
  
template <class Source>  
path(const Source& source);
  
template <class Source>  
path(const Source& source, const locale& loc);
  
template <class InIt>  
path(InIt first, InIt last);
  
template <class InIt>  
path(InIt first, InIt last, const locale& loc);
```  
  
 Tüm oluşturucular çeşitli şekillerde myname oluşturun:  
  
 İçin Path() myname() olur.  
  
 Yolu için (const yolu & sağa) myname(right.myname) değil.  
  
 Yolu için (yolu & & sağa) myname(right.myname) değil.  
  
 Şablon için\<kaynak sınıfı > yol (const kaynak & kaynak) myname(source) değil.  
  
 Şablon için\<kaynak sınıf > yol (const kaynak kaynağı, const yerel ayar & loc) loc tüm gerekli codecvt modelleri alma myname(source) olduğu  
  
 Şablon için\<InIt sınıfı > yol (Init ilk, Init son) myname olduğu (ilk, son).  
  
 Şablon için\<InIt sınıfı > yolu (Init ilk, Init son, const yerel ayar & loc) myname olduğu (ilk, son), gerekli codecvt modelleri loc gelen herhangi alma  
  
## <a name="pathpreferredseparator"></a>PATH::preferred_separator  
  
```cpp  
#if _WIN32_C_LIB  
static constexpr value_type preferred_separator == L'\\';  
#else // assume Posix  
static constexpr value_type preferred_separator == '/';  
#endif // filesystem model now defined  
```  
  
 Sabit nesnesi, konak işletim sistemine bağlı olarak yol bileşenlerini ayırmak için tercih edilen karakter sağlar. Onun yerine '/' L kullanmak için Windows altında çoğu bağlamlarda eşit bulunmadığı olduğuna dikkat edin.  
  
## <a name="pathrelativepath"></a>PATH::relative_path  
  
```cpp  
path relative_path() const;
```  
  
 Myname, özellikle root_path().native() ve hemen sonraki yedekli dizin ayırıcı kaldırdıktan sonra myname soneki göreli yol bileşenini döndürür. Bileşen boş olabilir.  
  
## <a name="pathremovefilename"></a>PATH::remove_filename  
  
```cpp  
path& remove_filename();
```  
  
## <a name="pathreplaceextension"></a>PATH::replace_extension  
  
```cpp  
path& replace_extension(const path& newext = path());
```  
  
 Üye işlevini soneki extension().native() myname ilk kaldırır. Ardından IF! newext.empty() & & newext [0]! nokta = (nokta olduğu * path("."). c_str()) sonra nokta için myname eklenir. Ardından newext için myname eklenir.  
  
## <a name="pathreplacefilename"></a>PATH::replace_filename  
  
```cpp  
path& replace_filename(const path& pval);
```  
  
 Üye işlevini çalıştırır:  
  
```cpp  
remove_filename();

*this /= pval;  
return (*this);
```  
  
## <a name="pathrootdirectory"></a>PATH::root_directory  
  
```cpp  
path root_directory() const;
```  
  
 Myname kök dizin bileşenini döndürür. Bileşen boş olabilir.  
  
## <a name="pathrootname"></a>PATH::root_name  
  
```cpp  
path root_name() const;
```  
  
 Myname kök adı bileşenini döndürür. Bileşen boş olabilir.  
  
## <a name="pathrootpath"></a>PATH::root_path  
  
```cpp  
path root_path() const;
```  
  
 Myname, özellikle root_name() kök yolu bileşenini döndürür / root_directory. Bileşen boş olabilir.  
  
## <a name="pathstem"></a>PATH::stem  
  
```cpp  
path stem() const;
```  
  
 Myname, özellikle filename().native() kaldırılan tüm sonunda extension().native() ile stem bileşenini döndürür. Bileşen boş olabilir.  
  
## <a name="pathstring"></a>PATH::String  
  
```cpp  
template \<class Elem, class Traits = char_traits\<Elem>, class Alloc = allocator\<Elem>>  
basic_string\<Elem, Traits, Alloc> string(const Alloc& al = Alloc()) const; 
string string() const;
```  
  
 İlk (şablonu) üye işlevi aynı şekilde YOLUM içinde depolanan dizisi dönüştürür:  
  
1.  dize String()\<char, özellikleri, ayırma >)  
  
2.  dize wstring()\<wchar_t, özellikleri, ayırma >)  
  
3.  dize u16string()\<char16_t, özellikleri, ayırma >)  
  
4.  dize u32string()\<char32_t, özellikleri, ayırma >)  
  
 İkinci üye işlevi bir karakter dizisi için ana bilgisayar sistemi tarafından avantajlı kodlama için YOLUM depolanan dizisi dönüştürür ve dize türünde bir nesnede depolanan döndürür.  
  
## <a name="pathstringtype"></a>PATH::string_type  
  
```cpp  
typedef basic_string<value_type> string_type;  
```  
  
 Basic_string < value_type > eşanlamlısı türüdür.  
  
## <a name="pathswap"></a>PATH::Swap  
  
```cpp  
void swap(path& right) noexcept;  
```  
  
 Swap (YOLUM, right.mypath) yürütür.  
  
## <a name="pathu16string"></a>PATH::u16string  
  
```cpp  
u16string u16string() const;
```  
  
 Üye işlevini UTF-16 YOLUM depolanan dizisi dönüştürür ve bir türü u16string nesnesinde depolanan döndürür.  
  
## <a name="pathu32string"></a>PATH::u32string  
  
```cpp  
u32string u32string() const;
```  
  
 Üye işlevini UTF-32 YOLUM depolanan dizisi dönüştürür ve bir türü u32string nesnesinde depolanan döndürür.  
  
## <a name="pathu8string"></a>PATH::u8string  
  
```cpp  
string u8string() const;
```  
  
 Üye işlevini UTF-8 YOLUM depolanan dizisi dönüştürür ve bir türü u8string nesnesinde depolanan döndürür.  
  
## <a name="pathvaluetype"></a>PATH::value_type  
  
```cpp  
#if _WIN32_C_LIB  
typedef wchar_t value_type;  
#else // assume Posix  
typedef char value_type;  
#endif // filesystem model now defined  
```  
  
 Türü ana bilgisayar işletim sistemi tarafından avantajlı yolu öğelerini açıklar.  
  
## <a name="pathwstring"></a>PATH::wstring  
  
```cpp  
wstring wstring() const;
```  
  
 Wchar_t sıralı bir ana bilgisayar sistemi tarafından avantajlı kodlama için YOLUM depolanan dizisi dönüştürür ve bir türü wstring nesnesinde depolanan döndürür.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<filesystem >  
  
 **Namespace:** std::experimental::filesystem
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Üstbilgi dosyaları başvurusu](../standard-library/cpp-standard-library-header-files.md)

