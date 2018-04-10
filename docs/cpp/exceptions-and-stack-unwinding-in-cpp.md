---
title: Özel durumlar ve yığını geriye doğru izleme c++'ta | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
ms.assetid: a1a57eae-5fc5-4c49-824f-3ce2eb8129ed
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b2b354ebaa72c5257e2752a948ece6320a5d8e70
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exceptions-and-stack-unwinding-in-c"></a>C++'da Özel Durumlar ve Yığını Geriye Doğru İzleme
C++ özel durum mekanizmasında denetim, throw deyiminden throw türünü işleyebilen ilk catch deyimine geçer. Catch deyimi ulaşıldığında, tüm kapsamında arasında throw ve catch deyimleri otomatik değişkenleri olarak bilinen bir işlemle yok *yığın geriye doğru izleme*. Yığın geriye doğru izleme işleminde, yürütme aşağıdaki gibi olur:  
  
1.  Denetim `try` deyimine normal sıralı yürütme ile ulaşır. `try` bloğundaki korunan bölüm yürütülür.  
  
2.  Korunan bölümün yürütülmesi sırasında hiçbir özel durum oluşturulmazsa, `catch` bloğunun izleyen `try` yan tümceleri yürütülmez. Yürütme işlemi, ilişkili `catch` bloğunu takip eden son `try` yan tümcesinden sonraki deyimden devam eder.  
  
3.  Korunan bölümün yürütülmesi sırasında veya korunan bölümün doğrudan veya dolaylı olarak çağırdığı bir yordam sırasında bir özel durum oluşturulursa, `throw` işleneni tarafından oluşturulan nesneden bir özel durum nesnesi oluşturulur. (Bu, bir kopya oluşturucusunu da işin içine katabilir.) Bu noktada derleyici, daha üst bir yürütme bağlamında, oluşturulan türde bir özel durumu işleyebilen bir `catch` yan tümcesi veya her tür özel durumu işleyebilen bir `catch` işleyicisi arar. Bu `catch` işleyicileri, `try` bloğundan sonra göründükleri sırayla incelenir. Uygun bir işleyici bulunmazsa, dinamik olarak kapsayan bir sonraki `try` bloğu incelenir. Bu işlem, en dıştaki kapsayan `try` bloğu incelenene kadar devam eder.  
  
4.  Eşleşen bir işleyici hala bulunamazsa ya da geriye doğru işlem sırasında işleyici denetimi almadan önce bir özel durum oluşursa, önceden tanımlanmış çalışma zamanı işlevi `terminate` çağrılır. Özel durum, geriye doğru izleme başlamadan önce ve bir özel durum oluştuktan sonra oluşursa, `terminate` çağrılır.  
  
5.  Eşleşen bir `catch` işleyicisi bulunursa ve değere göre yakalarsa, özel durum nesnesi kopyalanarak biçimsel parametresi başlatılır. Başvuruya göre yakalarsa, parametre özel durum nesnesine başvurmak için başlatılır. Biçimsel parametre başlatıldıktan sonra, yığını geriye doğru izleme işlemi başlar. Bu, `try` işleyicisiyle ilişkili `catch` bloğunun başlangıcı ile özel durumun oluşturulma alanı arasında, tam olarak oluşturulmuş ancak henüz yok edilmemiş tüm otomatik nesnelerin yok edilmesini içerir. Yok etme işlemi oluşturma işleminin ters sırasıyla yapılır. `catch` işleyicisi yürütülür ve program son işleyiciden (yani `catch` işleyicisi olmayan ilk deyim veya oluşturma) sonra yürütme işlemine devam eder. Denetim, `catch` deyimi veya bir `goto` deyimindeki `case` etiketi aracılığıyla değil, yalnızca oluşturulan bir özel durumla bir `switch` işleyicisi girebilir.  
  
## <a name="stack-unwinding-example"></a>Yığın Geriye Doğru İzleme Örneği  
 Aşağıdaki örnek, bir özel durum oluştuğunda yığının nasıl geriye doğru izlediğini gösterir. İş parçacığı üzerindeki yürütme, `C` içindeki throw deyiminden `main` içindeki catch deyimine atlar ve yol boyunca her işlevi geriye doğru alır. `Dummy` nesnelerinin oluşturulduğu ve ardından kapsam dışına çıkarken yok edildikleri sıralamaya dikkat edin. Ayrıca, catch deyimini içeren `main` haricinde, hiçbir işlevin tamamlamadığına dikkat edin. `A` işlevi `B()` için yaptığı çağrıdan, `B` işlevi de `C()` için yaptığı çağrıdan hiçbir zaman dönmez. `Dummy` işaretçisine ve ilişkili delete deyiminin tanımına ilişkin açıklamayı kaldırır ve ardından programı çalıştırırsanız, işaretçinin asla silinmediğine dikkat edin. Bu, işlevler özel durum sağlamadığında neler olabileceğini gösterir. Daha fazla bilgi için bkz. Nasıl yapılır: Özel Durumlar için Tasarım. Catch deyimi için açıklama satırı yaparsanız, işlenmemiş bir özel durum nedeniyle bir program sonlandığında ne olacağını görebilirsiniz.  
  
```  
#include <string>  
#include <iostream>  
using namespace std;  
  
class MyException{};  
class Dummy  
{  
    public:  
    Dummy(string s) : MyName(s) { PrintMsg("Created Dummy:"); }  
    Dummy(const Dummy& other) : MyName(other.MyName){ PrintMsg("Copy created Dummy:"); }  
    ~Dummy(){ PrintMsg("Destroyed Dummy:"); }  
    void PrintMsg(string s) { cout << s  << MyName <<  endl; }  
    string MyName;   
    int level;  
};  
  
void C(Dummy d, int i)  
{   
    cout << "Entering FunctionC" << endl;  
    d.MyName = " C";  
    throw MyException();     
  
    cout << "Exiting FunctionC" << endl;  
}  
  
void B(Dummy d, int i)  
{  
    cout << "Entering FunctionB" << endl;  
    d.MyName = "B";  
    C(d, i + 1);     
    cout << "Exiting FunctionB" << endl;   
}  
  
void A(Dummy d, int i)  
{   
    cout << "Entering FunctionA" << endl;  
    d.MyName = " A" ;  
  //  Dummy* pd = new Dummy("new Dummy"); //Not exception safe!!!  
    B(d, i + 1);  
 //   delete pd;   
    cout << "Exiting FunctionA" << endl;     
}  
  
int main()  
{  
    cout << "Entering main" << endl;  
    try  
    {  
        Dummy d(" M");  
        A(d,1);  
    }  
    catch (MyException& e)  
    {  
        cout << "Caught an exception of type: " << typeid(e).name() << endl;  
    }  
  
    cout << "Exiting main." << endl;  
    char c;  
    cin >> c;  
}  
  
/* Output:  
    Entering main  
    Created Dummy: M  
    Copy created Dummy: M  
    Entering FunctionA  
    Copy created Dummy: A  
    Entering FunctionB  
    Copy created Dummy: B  
    Entering FunctionC  
    Destroyed Dummy: C  
    Destroyed Dummy: B  
    Destroyed Dummy: A  
    Destroyed Dummy: M  
    Caught an exception of type: class MyException  
    Exiting main.  
  
*/  
  
```