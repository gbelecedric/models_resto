### MODELS_resto :  groupe 5
### pages manquante



### mes_App


* Menu
##### page
>menu.html

>petitdej.html,
>dejeuner.thml,
>dessert.html,
>diner.html,
## supression des pages de special et on va les remplacer par deujerner.html et haute

* configuration
##### page
>aucune page
* Reservation
##### page
>reservation.html
* contact
##### page
>a creer
* Horraire
>aucune page
* Team
>team.html
* entreprise

##### page
>about.html
>index.html


### Mes_models

# Menu_model
```python
#---------------Menu------app-----#


class Timemodels(models.Model):
    date_add =  models.DateTimeField(auto_now_add=True)
    date_update =  models.DateTimeField(auto_now=True)
    class Meta:
         abstract = True
    
class Categorie(Timemodels):
    nom = models.CharField(max_length=255)
    
class Recette(Timemodels):
    categorie = models.ForeignKey(Categorie,on_delete=models.CASCADE, related_name="categories")
    nom = models.CharField(max_length=255)
    price = models.FloatField()
    ingrediens =  models.TextField()
    image = models.ImageField(upload_to='image',)
    
```   
# team_models
```python

#-------team-----#

class Personel (Timemodels):
    nom = models.CharField(max_length=250)
    image = models.ImageField(upload_to='image')
    fonction = models.CharField(max_length=250)
    facebook =  models.URLField(max_length=250)
    instagrame =  models.URLField(max_length=250)
    twitter =  models.URLField(max_length=250)
    googleplus =  models.URLField(max_length=250
    
```   
# Reservation..
```python

#----------------reservation-----------#
class Table (Timemodels):
     nom = models.CharField(max_length=255)
     person = models.IntegerField()
     disponible = models.BooleanField(default=True)
      




class reservation(Timemodels):
    phone = models.IntegerField()
    nom = models.CharField(max_length=255)
    email = models.EmailField()
    date = models.CharField()
    time = models.TimeField()
    message =  models.TextField()
    table = models.ForeignKey(Table,on_delete=models.CASCADE, related_name="tables")

``` 
# Horaire..
```python

#-----------Horaire-----------#

class Horaire(Timemodels):
    jour = models.CharField(max_length=255)
    ouverture = models.TimeField()
    fermeture = models.TimeField()
    fermer = models.BooleanField(default=False)

``` 
# Newsller
```python

#--------------Newsller-----------#

class newsller(Timemodels):
    email = models.EmailField()

```

# configuration

```python

#--------------CONfIGURATION-----------#

class footer(Timemodels):
    facebook =  models.URLField(max_length=250)
    instagrame =  models.URLField(max_length=250)
    twitter =  models.URLField(max_length=250)
    description_gauche_resto =  models.CharField(max_length=255)
    description_droite_neswletter =  models.CharField(max_length=255)
    
class about(Timemodels):
      description_about =  models.CharField(max_length=255)
      image = models.ImageField(upload_to='image',)


```
### Explication :

> bon je vois pas trop grande chose a expliquer 
> mais si vous ne comprennez pas un truc on peut se prendre sur whatssap 
> et je vais vous dire les pages a ajouter et element a suprimer entre les pages mais
> pour l'instant voici mon models dans toute sa  simplicité
> coter fonctionalité nous allons en parler aussi vos mieux les enumerés des maintenant


 
# Fin... 
