---
title: 'Nasıl yapılır: derleme uyumluluk sorunlarını tanılama ve düzeltme (C + +/ CLI) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- versioning, diagnosing conflicts
- versioning
- exceptions, diagnosing odd behavior
- compatibility, between assemblies
ms.assetid: 297c71e3-04a8-4d24-a5dc-b04a2c5cc6fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: d4440ab455aff8922c108cdb35cff041cd67f56d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-diagnose-and-fix-assembly-compatibility-problems-ccli"></a>Nasıl yapılır: Derleme Uyumluluk Sorunlarını Tanılama ve Düzeltme (C++/CLI)
Bu konuda, çalışma zamanında başvurulan derleme sürümü derleme zamanında başvurulan bir derleme sürümü eşleşmediğinde neler olabileceğini açıklanmıştır ve sorunu önlemenin.  
  
 İle bir derlemeyi derlendiğinde diğer derlemelerden başvurulabilir `#using` sözdizimi. Derleme sırasında bu derlemeler derleyici tarafından erişilir. Bu derlemelerden alınan bilgiler, en iyi duruma getirme kararlar almak için kullanılır.  
  
 Ancak, başvurulan derlemeyi değiştirilmiş ve yeniden derlenmesi ve kendisine bağımlı olan başvuru derlemesinin derlenir değil, derlemeler değiştirilemeyebilir hala uyumlu olmayabilir. Geçerli iyileştirme kararları ilk yeni derleme sürümü göre doğru olmayabilir. Bu uyumsuzluklar nedeniyle çeşitli çalışma zamanı hataları oluşabilir. Bu gibi durumlarda üretilen herhangi bir özel durum yoktur. Çalışma zamanında hata bildirilir yolu soruna neden olan kod değişikliğinin yapısına bağlıdır.  
  
 Tüm uygulama için ürününüzü'nın yayınlanan sürümüne yeniden sürece bu hatalar, son üretim kodunda bir sorun olmamalıdır. Ortak yayımlanan derlemeler bu sorunlardan kaçınılması sağlayacak bir resmi sürüm numarasıyla işaretlenmelidir. Daha fazla bilgi için bkz: [derleme sürümü oluşturma](/dotnet/framework/app-domains/assembly-versioning).  
  
### <a name="diagnosing-and-fixing-an-incompatibility-error"></a>Tanılama ve uyumsuzluk hatasını giderme  
  
1.  Çalışma zamanı özel durumları veya başka bir derlemeye başvuran kodda oluşan diğer hata koşulları karşılaşan ve başka tanımlanan neden varsa, eski bir derleme ilgilenme.  
  
2.  İlk olarak, yalıtmak ve özel durum ya da diğer hata koşulu yeniden oluşturun. Eski bir özel durum nedeniyle ortaya çıkan bir sorun tekrarlanabilir olmalıdır.  
  
3.  Zaman damgası uygulamanızda başvurulan derlemelerin denetleyin.  
  
4.  Başvurulan derlemelerin herhangi birinin zaman damgaları uygulamanızın son derleme zaman damgası sonraki varsa, uygulamanızın güncel değil. Bu gerçekleşirse, en son derleme uygulamanızla derlenir ve gerekli kod değişikliklerini yapın.  
  
5.  Uygulamayı yeniden çalıştırın, sorunu yeniden oluşturmak ve özel durum meydana gelmez doğrulama adımları uygulayın.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki programı bir yöntemin erişilebilirliğini azaltarak ve bu yöntem başka bir derlemede derlemeden erişmeye sorun gösterilmektedir. Derleme deneyin `changeaccess.cpp` ilk. Bu, değiştirecek derlemedir. Ardından derleme `referencing.cpp`. Derleme başarılı olur. Şimdi, çağrılan yöntemin erişilebilirliğini azaltın. Yeniden derleyin `changeaccess.cpp` bayrağıyla `/DCHANGE_ACCESS`. Artık de yasal adlı şekilde korumalı yerine özel, bu yöntem sağlar. Derlemeden `referencing.exe`, uygulamayı yeniden çalıştırın. Bir özel durum <xref:System.MethodAccessException> neden olur.  
  
```  
// changeaccess.cpp  
// compile with: /clr:safe /LD  
// After the initial compilation, add /DCHANGE_ACCESS and rerun  
// referencing.exe to introduce an error at runtime. To correct  
// the problem, recompile referencing.exe  
  
public ref class Test {  
#if defined(CHANGE_ACCESS)  
protected:  
#else  
public:  
#endif  
  
  int access_me() {  
    return 0;  
  }  
  
};  
  
```  
  
```  
// referencing.cpp  
// compile with: /clr:safe   
#using <changeaccess.dll>  
  
// Force the function to be inline, to override the compiler's own  
// algorithm.  
__forceinline  
int CallMethod(Test^ t) {  
  // The call is allowed only if access_me is declared public  
  return t->access_me();  
}  
  
int main() {  
  Test^ t = gcnew Test();  
  try  
  {  
    CallMethod(t);  
    System::Console::WriteLine("No exception.");  
  }  
  catch (System::Exception ^ e)  
  {  
    System::Console::WriteLine("Exception!");  
  }  
  return 0;  
}  
  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [#using yönergesi](../preprocessor/hash-using-directive-cpp.md)   
 [Yönetilen Türler (C++/CLI)](../dotnet/managed-types-cpp-cli.md)