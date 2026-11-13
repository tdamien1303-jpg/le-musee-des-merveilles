const STORAGE_KEY = 'museum_dataset_v1';
const SESSION_KEY = 'museum_session_v1';

function uid(prefix = 'item') {
  return `${prefix}-${Math.random().toString(36).slice(2, 9)}`;
}

function createExhibit(overrides = {}) {
  return {
    id: overrides.id || uid('exhibit'),
    name: overrides.name || 'Nouvelle exposition',
    category: overrides.category || 'Spécialité',
    country: overrides.country || 'Monde',
    region: overrides.region || 'Région',
    description: overrides.description || 'Description à compléter.',
    origin: overrides.origin || 'Origine non renseignée.',
    ingredients: overrides.ingredients || ['Ingrédient principal'],
    method: overrides.method || 'Préparation traditionnelle.',
    culturalNotes: overrides.culturalNotes || 'Signification culturelle à compléter.',
    anecdote: overrides.anecdote || 'Anecdote à ajouter.',
    facts: overrides.facts || ['Fait intéressant.'],
    image: overrides.image || 'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=80',
    images: overrides.images || [overrides.image || 'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=80'],
    voiceText: overrides.voiceText || 'Bienvenue dans le musée.',
    tags: overrides.tags || [],
    difficulty: overrides.difficulty || 'Moyenne',
    prepTime: overrides.prepTime || '20 min',
    cookTime: overrides.cookTime || '30 min',
    year: overrides.year || 'Histoire',
    animation: overrides.animation || 'Apparition progressive',
    active: overrides.active !== false,
  };
}

function defaultMuseum() {
  const rooms = [
    {
      id: 'salle-1',
      name: 'Salle 1 – Les trésors de la cuisine française',
      theme: 'Cuisine française',
      decor: 'Vitrines en bois doré, marbres et luminaires à la française',
      palette: '#d9b35d',
      mood: 'classique, élégante, épicée',
      guide: 'La plus belle cuisine terroir du monde.',
      exhibits: [
        createExhibit({
          id: 'pot-au-feu',
          name: 'Pot-au-feu',
          category: 'Plat traditionnel',
          country: 'France',
          region: 'Île-de-France',
          description: 'Un grand classique de la cuisine française, fondé sur une longue cuisson de viande et de légumes pour obtenir un bouillon généreux et un plat de famille.',
          origin: 'Le pot-au-feu est un symbole de la cuisine bourgeoise et rurale française, apprécié depuis plusieurs siècles.',
          ingredients: ['bœuf', 'carotte', 'poireau', 'navet', 'chou', 'os de veau'],
          method: 'On fait mijoter la viande avec des légumes et des aromates pendant plusieurs heures jusqu’à obtenir un bouillon clair et un plat savoureux.',
          culturalNotes: 'Il représente l’art de la cuisine de terre, des familles et du partage.',
          anecdote: 'Le pot-au-feu a longtemps été le repas rassurant des foyers français, presque autant que la pâte à tartiner.',
          facts: ['Le bouillon obtenu est souvent servi en début de repas.', 'Le pot-au-feu est parfois associé à la cuisine de dimanche.'],
          image: 'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1559847844-5315695dadae?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Bienvenue dans la cuisine française. Voici le pot-au-feu, un plat de famille aux saveurs profondes, symbole de la tradition française et de la richesse du bouillon.',
          tags: ['France', 'tradition', 'plat principal'],
          difficulty: 'Facile',
          prepTime: '30 min',
          cookTime: '3 h',
          animation: 'Ébullition douce et vapeur légère',
        }),
        createExhibit({
          id: 'bouillabaisse',
          name: 'Bouillabaisse',
          category: 'Spécialité méditerranéenne',
          country: 'France',
          region: 'Provence',
          description: 'Une soupe de poisson emblématique du sud de la France, préparée avec des poissons variés et des herbes aromatiques.',
          origin: 'Originaire de Marseille et de ses ports, la bouillabaisse raconte le commerce, la mer et les marchés de Provence.',
          ingredients: ['poissons de roche', 'rascasse', 'lotte', 'huile d’olive', 'safran', 'aioli'],
          method: 'Les poissons sont cuits dans un court bouillon parfumé au safran et aux herbes, ensuite servis avec du pain et de la rouille.',
          culturalNotes: 'Elle illustre le lien fort entre la cuisine provençale et les traditions portuaires.',
          anecdote: 'Autrefois, les poissons de moindre valeur alimentaient le bouillon, tandis que les morceaux nobles étaient servis avec la soupe.',
          facts: ['Le safran donne sa couleur orangée caractéristique.', 'Le mot bouillabaisse vient du provençal.»'],
          image: 'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La bouillabaisse est un voyage dans la Méditerranée. Sa couleur, ses arômes et ses poissons font de cette soupe une vraie œuvre culinaire provençale.',
          tags: ['France', 'mer', 'soupe'],
          difficulty: 'Moyenne',
          prepTime: '45 min',
          cookTime: '50 min',
          animation: 'Ébullition de bouillon et parfums marins',
        }),
        createExhibit({
          id: 'tarte-tatin',
          name: 'Tarte Tatin',
          category: 'Dessert',
          country: 'France',
          region: 'Loire',
          description: 'Un dessert de pommes caramélisées, cuit à l’envers, qui se révèle d’une élégance simple et généreuse.',
          origin: 'Le dessert tient son nom de la famille Tatin, qui l’aurait élaboré dans le Loiret.',
          ingredients: ['pommes', 'sucre', 'beurre', 'pâte brisée'],
          method: 'Les pommes sont caramélisées au beurre et au sucre, puis la pâte est recouverte avant la cuisson et retournée au moment de servir.',
          culturalNotes: 'Un dessert qui célèbre l’équilibre entre rusticité et finesse.',
          anecdote: 'Selon la légende, elle a été créée par accident lorsque la pâtissière oublia une tarte au fond du four.',
          facts: ['Les pommes doivent être fermes pour garder leur forme.', 'Son goût est à la fois fruité, tendre et caramélisé.'],
          image: 'https://images.unsplash.com/photo-1517433670267-08bbd4be890f?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1517433670267-08bbd4be890f?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La tarte Tatin est la gourmandise du hasard heureux. Son caramel profond et ses pommes fondantes en font un dessert d’exception.',
          tags: ['France', 'dessert', 'pommes'],
          difficulty: 'Moyenne',
          prepTime: '25 min',
          cookTime: '45 min',
          animation: 'Caramélisation lente et retournement du dessert',
        })
      ]
    },
    {
      id: 'salle-2',
      name: 'Salle 2 – Les cuisines d’Europe',
      theme: 'Europe',
      decor: 'Cartes du continent, vitrines nordiques et méditerranéennes',
      palette: '#8ecae6',
      mood: 'culturelle, variée, festive',
      guide: 'L’Europe en un voyage gustatif.',
      exhibits: [
        createExhibit({
          id: 'paella',
          name: 'Paella',
          category: 'Plat emblématique',
          country: 'Espagne',
          region: 'Valence',
          description: 'Un plat de riz généreux préparé avec des fruits de mer, des légumes, de la viande ou du poisson et des épices.',
          origin: 'La paella trouve ses racines dans les traditions agricoles et maritimes de la région de Valence.',
          ingredients: ['riz', 'poulet', 'fruits de mer', 'poivron', 'tomates', 'safran'],
          method: 'Le riz est cuit dans un bouillon parfumé jusqu’à former une croûte dorée au fond de la poêle.',
          culturalNotes: 'La paella illustre la convivialité espagnole et le goût pour les festins de partage.',
          anecdote: 'La paella est souvent préparée dans des paelles géantes pour les fêtes et rassemblements.',
          facts: ['La partie dorée du fond est très prisée.', 'Le safran est l’un des éléments les plus reconnaissables de la recette.'],
          image: 'https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1519708227418-c8fd9a32b7a2?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1559847844-5315695dadae?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La paella est une ode au partage. Elle mélange riz, saumon, légumes et safran dans un plat généreux et monumental.',
          tags: ['Espagne', 'riz', 'plat principal'],
          difficulty: 'Moyenne',
          prepTime: '35 min',
          cookTime: '45 min',
          animation: 'Mélange de textures et dorure des grains de riz',
        }),
        createExhibit({
          id: 'gnocchi',
          name: 'Gnocchi',
          category: 'Pâtes traditionnelles',
          country: 'Italie',
          region: 'Piémont',
          description: 'De petites boules de pâte de pommes de terre, souvent accompagnées d’une sauce simple et parfumée.',
          origin: 'Les gnocchi sont un héritage culinaire italien, connu sous plusieurs versions selon les régions.',
          ingredients: ['pommes de terre', 'farine', 'beurre', 'parmesan', 'basilic'],
          method: 'La pâte est façonnée puis cuite dans de l’eau avant d’être servie avec une sauce.',
          culturalNotes: 'À l’approche du jeudi, les gnocchi sont traditionnels en Italie dans certaines familles.',
          anecdote: 'Les gnocchi ont été associés à des traditions calendaires et au partage familial.',
          facts: ['Ils peuvent être préparés avec des pommes de terre, mais aussi de la semoule selon les zones.', 'Les variantes des gnocchi sont omniprésentes dans l’Italie rurale.'],
          image: 'https://images.unsplash.com/photo-1621996346565-e3dbc646d9a9?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1621996346565-e3dbc646d9a9?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1555949258-eb67b1ef0ceb?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Les gnocchi incarnent la cuisine italienne faite de simplicité et de talent. Leur texture moelleuse et leur sauce parfumée les rendent immédiatement reconnaissables.',
          tags: ['Italie', 'pâtes', 'tradition'],
          difficulty: 'Facile',
          prepTime: '30 min',
          cookTime: '20 min',
          animation: 'Mouvement de pâte et sauce enveloppante',
        }),
        createExhibit({
          id: 'goulash',
          name: 'Goulash',
          category: 'Ragoût',
          country: 'Hongrie',
          region: 'Puszta',
          description: 'Un ragoût de bœuf longuement mijoté avec des oignons et des épices, souvent servi avec des pâtes ou du pain.',
          origin: 'Le goulash est lié à la cuisine hongroise et à la tradition pastorale des plaines.',
          ingredients: ['bœuf', 'oignon', 'paprika', 'poivron', 'tomates'],
          method: 'Le bœuf est mijoté lentement en évitant de trop cuire afin de garder sa tendreté.',
          culturalNotes: 'La paprica est l’élément fondamental de sa couleur et de son goût.',
          anecdote: 'Le goulash a évolué des préparations de campement vers les traditions de table de la cuisine urbaine.',
          facts: ['Le paprika est parfois doux ou fumé selon les recettes.', 'Le mot goulash est parfois utilisé pour désigner ses variantes de ragoût.'],
          image: 'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le goulash hongrois est un classique de la cuisine des steppes. Sa couleur, son parfum et sa rusticité en font une spécialité chaleureuse.',
          tags: ['Hongrie', 'ragoût', 'épices'],
          difficulty: 'Moyenne',
          prepTime: '20 min',
          cookTime: '2 h',
          animation: 'Mijotage lent et fond de sauce épicée',
        })
      ]
    },
    {
      id: 'salle-3',
      name: 'Salle 3 – Les cuisines d’Afrique',
      theme: 'Afrique',
      decor: 'Palette chaude, textures terre et lanternes orientées vers les marchés',
      palette: '#cc8a3c',
      mood: 'vivante, colorée, généreuse',
      guide: 'Le continent africain dans une célébration de saveurs.',
      exhibits: [
        createExhibit({
          id: 'couscous',
          name: 'Couscous',
          category: 'Plat traditionnel',
          country: 'Algérie',
          region: 'Maghreb',
          description: 'Un plat emblématique à base de semoule servi avec viande, légumes et sauce parfumée.',
          origin: 'Le couscous est profondément inscrit dans la table maghrébine et dans les traditions familiales.',
          ingredients: ['semoule', 'agneau', 'carotte', 'courgette', 'poivron', 'épices'],
          method: 'La semoule est préparée puis cuite à la vapeur et accompagnée d’un bouillon où mijotent légumes et viande.',
          culturalNotes: 'Le couscous est un symbole d’hospitalité et de rassemblement autour des tables.',
          anecdote: 'Le couscous est aussi un plat de fêtes, préparé pour les grandes occasions comme les mariages ou les rassemblements familiaux.',
          facts: ['La semoule est souvent préparée à partir de blé dur.', 'Le couscous est parfois servi dans des pots ou des grands plats offerts à plusieurs convives.'],
          image: 'https://images.unsplash.com/photo-1547592166-23ac45744acd?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1547592166-23ac45744acd?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le couscous est un joyau du Maghreb. Sa semoule aérienne, ses légumes et ses épices font de ce plat un moment de partage et de mémoire.',
          tags: ['Maghreb', 'semoule', 'partage'],
          difficulty: 'Moyenne',
          prepTime: '40 min',
          cookTime: '1 h',
          animation: 'Vapeur douce sur la semoule et mélange des épices',
        }),
        createExhibit({
          id: 'jollof-rice',
          name: 'Jollof rice',
          category: 'Plat festif',
          country: 'Ghana',
          region: 'Afrique de l’Ouest',
          description: 'Un riz parfumé cuit avec des tomates, des oignons, des épices et souvent accompagné de poulet ou de poisson.',
          origin: 'Le jollof rice est un classique de l’Afrique de l’Ouest, apprécié partout dans les célébrations.',
          ingredients: ['riz', 'tomates', 'oignon', 'poulet', 'poivre', 'piment'],
          method: 'Les épices et le bouillon sont longuement mélangés avant de cuire le riz jusqu’à ce qu’il absorbe les saveurs.',
          culturalNotes: 'Il est souvent servi lors des mariages, fêtes et grands rassemblements.',
          anecdote: 'C’est l’une des recettes africaines les plus célèbres et les plus discutées au niveau de la table',
          facts: ['Il existe de nombreuses variantes selon les pays de la région.', 'Le riz peut être préparé avec des légumes, du poisson, du poulet ou du bœuf.'],
          image: 'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1517248135467-4c7edcad34c4?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le jollof rice est un plat de fête, à la fois chaleureux, coloré et festif. Il raconte la richesse des cuisines de l’Afrique de l’Ouest.',
          tags: ['Afrique', 'riz', 'festif'],
          difficulty: 'Moyenne',
          prepTime: '30 min',
          cookTime: '45 min',
          animation: 'Riz absorbant les saveurs et sauce tomate volumineuse',
        }),
        createExhibit({
          id: 'injera',
          name: 'Injera',
          category: 'Pain fermenté',
          country: 'Éthiopie',
          region: 'Horn of Africa',
          description: 'Un pain fin et spongieux, fermenté à base de teff, servi avec des plats épicés et des sauces.',
          origin: 'L’injera est un élément central de la table éthiopienne et une base des repas communautaires.',
          ingredients: ['teff', 'eau', 'levure', 'farine'],
          method: 'La farine de teff est mélangée à de l’eau et laissée à fermenter avant d’être cuite sur une plaque chaude.',
          culturalNotes: 'Le pain sert de cuillère, de support et d’élément de partage.',
          anecdote: 'Le teff est une céréale ancienne, particulièrement appréciée pour ses qualités nutritionnelles.',
          facts: ['L’injera est souvent servie avec des lentilles, des épices et des légumes.', 'Sa texture spongieuse aide à absorber les sauces.'],
          image: 'https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1547592166-23ac45744acd?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'L’injera est plus qu’un pain. C’est un symbole de partage, de fermentation et de convivialité dans la cuisine éthiopienne.',
          tags: ['Éthiopie', 'pain', 'fermentation'],
          difficulty: 'Moyenne',
          prepTime: '20 min',
          cookTime: '30 min',
          animation: 'Fermentation et cuisson sur plaque',
        })
      ]
    },
    {
      id: 'salle-4',
      name: 'Salle 4 – Les cuisines d’Asie',
      theme: 'Asie',
      decor: 'Mangroves, lanternes et murs profonds en simili soie',
      palette: '#fa8d66',
      mood: 'luxe, apaisé, aromatique',
      guide: 'L’Asie sous toutes ses saveurs.',
      exhibits: [
        createExhibit({
          id: 'ramen',
          name: 'Ramen',
          category: 'Soupe',
          country: 'Japon',
          region: 'Tokyo',
          description: 'Une soupe de nouilles parfumée, souvent servie avec un bouillon clair ou riche, des œufs et de la viande.',
          origin: 'Le ramen est devenu un symbole culinaire contemporain du Japon, avec de multiples variations régionales.',
          ingredients: ['nouilles', 'bouillon', 'porc', 'œuf', 'algue', 'oignon'],
          method: 'Les nouilles sont servies dans un bouillon longuement préparé puis garnies de légumes, œufs et viandes.',
          culturalNotes: 'Le ramen raconte la culture des ramen shops, des petites cuisines urbaines, de la vitesse et du partage.',
          anecdote: 'Le ramen est souvent associé aux cafés de nuit et à la culture japonaise contemporaine.',
          facts: ['Le bouillon peut être basé sur du poisson, du porc ou des légumes.', 'Le ramen a traversé les siècles avec de nombreuses évolutions.'],
          image: 'https://images.unsplash.com/photo-1557872943-16a5ac26437e?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1557872943-16a5ac26437e?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1547592180-85f173990554?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le ramen est un voyage immédiat dans la cuisine japonaise. Sa préparation fine, ses nouilles et son bouillon dessinent un univers de chaleur et de subtilité.',
          tags: ['Japon', 'soupe', 'nouilles'],
          difficulty: 'Moyenne',
          prepTime: '30 min',
          cookTime: '45 min',
          animation: 'Bouillon fumant et gouttes de condensation',
        }),
        createExhibit({
          id: 'bibimbap',
          name: 'Bibimbap',
          category: 'Bol de riz',
          country: 'Corée du Sud',
          region: 'Séoul',
          description: 'Un bol de riz garni de légumes, œuf, viande et sauce gochujang, souvent mélangé au moment de servir.',
          origin: 'Originaire de la cuisine coréenne, le bibimbap est un symbole de l’équilibre des saveurs et des textures.',
          ingredients: ['riz', 'carotte', 'épinard', 'œuf', 'bœuf', 'gochujang'],
          method: 'Les ingrédients sont disposés séparément puis mélangés juste avant la dégustation pour garder leur texture.',
          culturalNotes: 'Le bibimbap évoque l’harmonie entre les couleurs, les saveurs et les nutriments.',
          anecdote: 'Son nom signifie littéralement « riz mélangé » et reflète le geste de la table avant de manger.',
          facts: ['La sauce piquante va de douce à intense selon la recette.', 'Le mélange final est central dans l’expérience gustative.'],
          image: 'https://images.unsplash.com/photo-1512058564366-18510be2db19?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1512058564366-18510be2db19?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le bibimbap est une composition précise et équilibrée. Chaque ingrédient apporte une texture et un goût distinct au moment du mélange.',
          tags: ['Corée', 'riz', 'équilibre'],
          difficulty: 'Facile',
          prepTime: '25 min',
          cookTime: '20 min',
          animation: 'Mélange de couleurs et réduction de sauce',
        }),
        createExhibit({
          id: 'pad-thai',
          name: 'Pad Thaï',
          category: 'Nouilles sautées',
          country: 'Thaïlande',
          region: 'Bangkok',
          description: 'Des nouilles sautées avec du tofu, du poisson, des légumes, de l’œuf et une sauce équilibrant acidité, douceur et piquant.',
          origin: 'Le pad thaï a été popularisé dans les cuisines thaïlandaises urbaines et est devenu un classique international.',
          ingredients: ['nouilles de riz', 'tofu', 'œuf', 'crevette', 'légumes', 'sauce tamarin'],
          method: 'Les nouilles sont sautées à feu vif puis assaisonnées avec une sauce au tamarin et au poisson.',
          culturalNotes: 'Il reflète la cuisine thaïlandaise avec son équilibre subtil entre doux, salé, acide et épicé.',
          anecdote: 'Le pad thaï est souvent servi avec des cacahuètes concassées et un morceau de citron vert.',
          facts: ['Le wok permet une cuisson rapide et intense.', 'Le goût final dépend fortement de l’équilibre entre les sauces.'],
          image: 'https://images.unsplash.com/photo-1512058564366-18510be2db19?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1512058564366-18510be2db19?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1559847844-5315695dadae?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le pad thaï est un exemple parfait de cuisine thaïlandaise : rapide, équilibrée et pleine de contrastes. Les nouilles sont au cœur du spectacle.',
          tags: ['Thaïlande', 'nouilles', 'sauté'],
          difficulty: 'Moyenne',
          prepTime: '20 min',
          cookTime: '15 min',
          animation: 'Cuisson à feu vif et éclat des sauces',
        })
      ]
    },
    {
      id: 'salle-5',
      name: 'Salle 5 – Les cuisines des Amériques',
      theme: 'Amériques',
      decor: 'Vitrines de terroir et rayons de soleil tropical',
      palette: '#b5d692',
      mood: 'brillant, festif, généreux',
      guide: 'Des saveurs qui traversent les continents.',
      exhibits: [
        createExhibit({
          id: 'tacos',
          name: 'Tacos',
          category: 'Street food',
          country: 'Mexique',
          region: 'Mexico',
          description: 'Des tortillas garnies de viande, légumes, fromage, salsa et herbes fraîches.',
          origin: 'Le taco est un classique de la cuisine mexicaine, apprécié partout dans le monde.',
          ingredients: ['tortillas', 'viande', 'oignon', 'persil', 'salsa', 'avocat'],
          method: 'On garnit la tortilla puis on la sert chaude avec des condiments.',
          culturalNotes: 'Les tacos sont souvent associés aux marchés et aux rues animées du Mexique.',
          anecdote: 'Leur simplicité cache des variations très régionales selon les ingrédients locaux.',
          facts: ['La tortilla est à la base de nombreuses recettes mexicaines.', 'Les tacos peuvent être préparés avec des viandes, des légumes ou du poisson.'],
          image: 'https://images.unsplash.com/photo-1552332386-f8dd00dc2f85?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1552332386-f8dd00dc2f85?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1604908176997-125f25cc6f3d?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Les tacos sont la cuisine de rue par excellence : colorés, souples et remplis de saveurs.',
          tags: ['Mexique', 'street food', 'tortillas'],
          difficulty: 'Facile',
          prepTime: '20 min',
          cookTime: '15 min',
          animation: 'Garniture vive et pliage de tortilla',
        }),
        createExhibit({
          id: 'feijoada',
          name: 'Feijoada',
          category: 'Plat de cassoulet',
          country: 'Brésil',
          region: 'São Paulo',
          description: 'Un plat de haricots noirs mijotés avec des morceaux de viande, aromatisés à l’ail et aux oignons.',
          origin: 'La feijoada est un classique de la cuisine brésilienne, liée aux traditions portugaises et latino-américaines.',
          ingredients: ['haricots noirs', 'porc', 'bœuf', 'oignon', 'ail', 'orange'],
          method: 'Les haricots sont mijotés longtemps avec les viandes jusqu’à obtenir un plat immense et savoureux.',
          culturalNotes: 'Il est souvent servi en famille, surtout lors des grandes réunions.',
          anecdote: 'La feijoada est aussi connue comme un plat festif des familles brésiliennes.',
          facts: ['Elle est parfois servie avec du riz, de la salade et de la farine de manioc.', 'Sa richesse correspond à un plat de partage.'],
          image: 'https://images.unsplash.com/photo-1604908176997-125f25cc6f3d?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1604908176997-125f25cc6f3d?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1552332386-f8dd00dc2f85?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La feijoada est un grand plat de partage brésilien, riche en textures et en traditions.',
          tags: ['Brésil', 'haricots', 'family'],
          difficulty: 'Moyenne',
          prepTime: '30 min',
          cookTime: '2 h',
          animation: 'Mijotage long et vapeur dense',
        }),
        createExhibit({
          id: 'ceviche',
          name: 'Ceviche',
          category: 'Poisson cru',
          country: 'Pérou',
          region: 'Lima',
          description: 'Du poisson mariné dans du citron vert, servi avec des oignons, de la coriandre et des légumes.',
          origin: 'Le ceviche est un classique des cuisines andines et côtières du Pérou.',
          ingredients: ['poisson', 'citron vert', 'oignon', 'coriandre', 'piment'],
          method: 'Le poisson est rapidement mariné dans les agrumes jusqu’à se tendre et à révéler un goût vif.',
          culturalNotes: 'C’est une préparation qui associe fraîcheur, acide et piquant.',
          anecdote: 'Le ceviche est souvent préparé à partir de poissons frais, très appréciés sur les côtes péruviennes.',
          facts: ['Le choix des agrumes est essentiel au goût final.', 'Le ceviche est une technique de marinade rapide et délicate.'],
          image: 'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1544025162-d76694265947?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1504674900247-0877df9cc836?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le ceviche est une cuisine au filet d’agrumes : vif, net et étonnant par sa fraicheur.',
          tags: ['Pérou', 'poisson', 'fraîcheur'],
          difficulty: 'Moyenne',
          prepTime: '20 min',
          cookTime: '0 min',
          animation: 'Marinade citronnée et éclat des saveurs',
        })
      ]
    },
    {
      id: 'salle-6',
      name: 'Salle 6 – Les desserts du monde',
      theme: 'Desserts',
      decor: 'Vitrines blanches, dorures et lumière douce de pâtisserie',
      palette: '#f7d9a4',
      mood: 'sucré, lumineux, raffiné',
      guide: 'Une galerie de douceurs entre tradition et invention.',
      exhibits: [
        createExhibit({
          id: 'baklava',
          name: 'Baklava',
          category: 'Pâtisserie',
          country: 'Turquie',
          region: 'Anatolie',
          description: 'Des feuilles de pâte phyllo feuilletées avec des noix et du miel, dorées au four.',
          origin: 'La baklava est une pâtisserie de tradition orientale, largement partagée dans les cuisines du Moyen-Orient et des Balkans.',
          ingredients: ['pâte filo', 'noix', 'beurre', 'sirop', 'miel'],
          method: 'Les feuilles de pâte sont superposées avec des noix puis cuites avant d’être nappées de sirop.',
          culturalNotes: 'C’est un dessert festif, partageable et symbolique de célébration.',
          anecdote: 'Le baklava est très présent dans les cérémonies et les repas de famille.',
          facts: ['Les variantes changent selon les noix, les épices et les sirops.', 'Le goût est à la fois croquant et fondant.'],
          image: 'https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1517433670267-08bbd4be890f?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La baklava est l’expression même du dessert festif et doré. Feuilletage, noix et sirop créent une texture exceptionnelle.',
          tags: ['Turquie', 'pâtisserie', 'miel'],
          difficulty: 'Moyenne',
          prepTime: '30 min',
          cookTime: '1 h',
          animation: 'Coulée de sirop et dorure de la pâte',
        }),
        createExhibit({
          id: 'mochi',
          name: 'Mochi',
          category: 'Pâtisserie glutinous',
          country: 'Japon',
          region: 'Honshu',
          description: 'Une galette de riz gluant, douce et souple, souvent garnie de pâte ou de fruits.',
          origin: 'Le mochi est profondément lié aux traditions japonaises et à la période festive.',
          ingredients: ['riz gluant', 'sucre', 'garnitures', 'farine'],
          method: 'Le riz est pilé puis malaxé avant de recevoir sa garniture ou sa forme finale.',
          culturalNotes: 'Le mochi est associé à la fête de l’an et aux repas du nouvel an japonais.',
          anecdote: 'Mélanger le riz et le sucre donne une pâte particulière très appréciée dans les desserts et en-cas.',
          facts: ['Le mochi a une texture très souple et adhérente.', 'L’atelier du pilage est souvent un moment festif.'],
          image: 'https://images.unsplash.com/photo-1601050690597-df0568f70950?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1601050690597-df0568f70950?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le mochi est un dessert délicat et visqueux, presque poétique. Sa texture est au cœur de son charme.',
          tags: ['Japon', 'riz', 'dessert'],
          difficulty: 'Moyenne',
          prepTime: '45 min',
          cookTime: '30 min',
          animation: 'Pavage du riz et sculpture douce',
        }),
        createExhibit({
          id: 'tiramisu',
          name: 'Tiramisu',
          category: 'Entremet',
          country: 'Italie',
          region: 'Venise',
          description: 'Un dessert de mascarpone, café et biscuits imbibés, nappé de cacao.',
          origin: 'Le tiramisu est un dessert moderne de la tradition italienne, très apprécié dans le monde entier.',
          ingredients: ['mascarpone', 'café', 'œufs', 'sucre', 'biscuits'],
          method: 'Les biscuits sont imbibés de café avant d’être superposés avec une crème légère.',
          culturalNotes: 'Il symbolise le plaisir de la table italienne et la recherche de textures suaves.',
          anecdote: 'Tiramisu signifie littéralement « tire-moi vers le haut » et fait référence à l’énergie du dessert.',
          facts: ['Le mascarpone et le café sont ses deux signatures.', 'Le goût est l’équilibre entre douceur, café et cacao.'],
          image: 'https://images.unsplash.com/photo-1571877227200-a0d98ea607e9?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1571877227200-a0d98ea607e9?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1551024601-bec78aea704b?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le tiramisu est un dessert qui mêle finesse et gourmandise. Son café et sa crème légère sont un duo irrésistible.',
          tags: ['Italie', 'café', 'entremet'],
          difficulty: 'Facile',
          prepTime: '20 min',
          cookTime: '0 min',
          animation: 'Coulée de cacao et couches douces',
        })
      ]
    },
    {
      id: 'salle-7',
      name: 'Salle 7 – Le royaume du chocolat',
      theme: 'Chocolat',
      decor: 'Lumières en bronze, vitrines de matière satinée et cacao en poudre',
      palette: '#8b5b3f',
      mood: 'luxueux, profond, velouté',
      guide: 'Le cacao en toute sa splendeur.',
      exhibits: [
        createExhibit({
          id: 'chocolat-noir',
          name: 'Chocolat noir',
          category: 'Cacao',
          country: 'Côte d’Ivoire',
          region: 'Afrique de l’Ouest',
          description: 'Un chocolat à forte teneur en cacao, utilisé pour ses arômes profonds et amers.',
          origin: 'Le cacao est cultivé en Afrique, puis transformé dans de nombreux pays pour des préparations fines et raffinées.',
          ingredients: ['fèves de cacao', 'sucre', 'beurre de cacao'],
          method: 'Les fèves sont torréfiées, broyées puis mélangées avec du sucre pour une texture fondante.',
          culturalNotes: 'Le chocolat noir est souvent perçu comme une expression de richesse et de complexité aromatique.',
          anecdote: 'Le cacao a inspiré des créations culinaires, des pralines, des truffes et des sculptures.',
          facts: ['Sa teneur en cacao varie selon les recettes.', 'Le cacao brut est riche en arômes intenses.'],
          image: 'https://images.unsplash.com/photo-1511381939415-e44015466834?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1511381939415-e44015466834?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1509440159596-0249088772ff?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le chocolat noir est une matière riche et profonde, qui révèle le cacao dans toute sa complexité.',
          tags: ['Cacao', 'chocolat', 'amertume'],
          difficulty: 'Facile',
          prepTime: '10 min',
          cookTime: '0 min',
          animation: 'Fusion et coulée de chocolat noir',
        }),
        createExhibit({
          id: 'truffes',
          name: 'Truffes au chocolat',
          category: 'Confiserie',
          country: 'France',
          region: 'Paris',
          description: 'Des boules de chocolat de différentes textures garnies de ganache, praliné ou fruits.',
          origin: 'Les truffes sont issues de la pâtisserie française et du savoir-faire des chocolatiers.',
          ingredients: ['chocolat', 'crème', 'beurre', 'cacao', 'garnitures'],
          method: 'Le chocolat est fondu puis façonné autour d’une ganache, puis roulé dans du cacao ou du sucre.',
          culturalNotes: 'Les truffes évoquent le luxe discret et l’élégance de la pâtisserie française.',
          anecdote: 'Leur forme ronde rappelle la truffe du sol, mais pas leur goût uniquement.',
          facts: ['Les truffes peuvent être préparées au chocolat noir, au lait ou blanc.', 'Le chocolat est souvent temperé pour une texture brillante.'],
          image: 'https://images.unsplash.com/photo-1588195538326-c5b1e9f80a1b?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1588195538326-c5b1e9f80a1b?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1511381939415-e44015466834?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Les truffes sont le luxe discret du chocolat. Elles sont à la fois élégantes, veloutées et pleines de surprises.',
          tags: ['France', 'truffe', 'confiserie'],
          difficulty: 'Moyenne',
          prepTime: '25 min',
          cookTime: '15 min',
          animation: 'Formage doux et poudre de cacao',
        }),
        createExhibit({
          id: 'chocolat-blanc',
          name: 'Chocolat blanc',
          category: 'Spécialité sucrée',
          country: 'Belgique',
          region: 'Bruxelles',
          description: 'Un chocolat doux, crémeux et très parfumé, préparé à partir de beurre de cacao et de sucre.',
          origin: 'Le chocolat blanc est une création moderne de la chocolaterie contemporaine, très populaire en Europe.',
          ingredients: ['beurre de cacao', 'lait', 'sucre', 'vanille'],
          method: 'Le beurre de cacao est fondu avec la matière laitière pour produire une texture douce et souple.',
          culturalNotes: 'Il est souvent associé à la pâtisserie fine et aux créations décoratives.',
          anecdote: 'Le chocolat blanc ne contient pas de pâte de cacao solide, mais garde la richesse aromatique du beurre de cacao.',
          facts: ['Il a un goût doux, crémeux et floral.', 'Il est souvent utilisé en glaçage et en ganache.'],
          image: 'https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1578985545062-69928b1d9587?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1588195538326-c5b1e9f80a1b?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le chocolat blanc est une matière douce et élégante. Son parfum de beurre de cacao apporte une touche douce et délicate.',
          tags: ['Belgique', 'chocolat', 'lait'],
          difficulty: 'Facile',
          prepTime: '10 min',
          cookTime: '0 min',
          animation: 'Fusion douce et finition glissante',
        })
      ]
    },
    {
      id: 'salle-8',
      name: 'Salle 8 – Les fruits du monde',
      theme: 'Fruits',
      decor: 'Vitrines lumineuses et murs en verre tropical',
      palette: '#7ed8a5',
      mood: 'vivant, exotique, éclatant',
      guide: 'Des fruits de rareté et de beauté.',
      exhibits: [
        createExhibit({
          id: 'durian',
          name: 'Durian',
          category: 'Fruit exotique',
          country: 'Thaïlande',
          region: 'Asie du Sud-Est',
          description: 'Un fruit aux épines, au goût intense et à l’odeur très marquée, connu comme l’un des plus controversés du monde.',
          origin: 'Le durian est un fruit tropical bien connu en Asie du Sud-Est.',
          ingredients: ['durian', 'sucre', 'lait', 'crème'],
          method: 'Le fruit est ouvert avec précaution puis servi frais, parfois dans des desserts.',
          culturalNotes: 'Il est souvent admiré pour son goût et redouté pour son odeur.',
          anecdote: 'Il a inspiré des discussions et des légendes parmi les amateurs de fruits exotiques.',
          facts: ['Son apparence est souvent comparée aux piquants d’un hérisson.', 'Les parfums peuvent varier selon la maturité.'],
          image: 'https://images.unsplash.com/photo-1615485290382-441e4d049cb5?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1615485290382-441e4d049cb5?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1502741338009-cac2772e18bc?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le durian est un fruit aux formes paradoxales : austère à l’extérieur, riche et intense à l’intérieur.',
          tags: ['Thaïlande', 'exotique', 'fruit'],
          difficulty: 'Facile',
          prepTime: '5 min',
          cookTime: '0 min',
          animation: 'Ouverture du fruit et éclat des arômes',
        }),
        createExhibit({
          id: 'kiwano',
          name: 'Kiwano',
          category: 'Fruit insolite',
          country: 'Afrique',
          region: 'Afrique australe',
          description: 'Un fruit de forme allongée, au goût frais et citronné, entouré d’épines vertes.',
          origin: 'Le kiwano est rameau d’un fruit exotique apprécié dans certaines régions tropicales.',
          ingredients: ['kiwano', 'citron', 'eau', 'sucre'],
          method: 'Le fruit est ouvert puis la pulpe est dégustée directement ou servie dans des préparations fraîches.',
          culturalNotes: 'Le kiwano séduit par son apparence si particulière qu’il est souvent présenté comme une curiosité.',
          anecdote: 'Il est souvent comparé à un fruit extraterrestre par son aspect.',
          facts: ['Sa pulpe est généreuse et très rafraîchissante.', 'Le goût est souvent décrit comme mêlant melon et agrume.'],
          image: 'https://images.unsplash.com/photo-1502741338009-cac2772e18bc?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1502741338009-cac2772e18bc?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1615485290382-441e4d049cb5?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le kiwano est le fruit de la curiosité. Son enveloppe épineuse cache des saveurs frais et exotiques.',
          tags: ['Afrique', 'rare', 'fruit'],
          difficulty: 'Facile',
          prepTime: '5 min',
          cookTime: '0 min',
          animation: 'Ouverture progressive et texture pulpeuse',
        }),
        createExhibit({
          id: 'mangoustan',
          name: 'Mangoustan',
          category: 'Fruit tropical',
          country: 'Malaisie',
          region: 'Asie du Sud-Est',
          description: 'Un fruit au goût doux et acidulé, à la peau violette ornée de petites pointes.',
          origin: 'Le mangoustan est un fruit tropical originellement présent dans les régions de l’Asie du Sud-Est.',
          ingredients: ['mangoustan', 'lait', 'sucre', 'eau'],
          method: 'Le fruit est ouvert délicatement et ses segments sont consommés frais.',
          culturalNotes: 'Il est souvent vanté comme un fruit de luxe et de fraîcheur.',
          anecdote: 'Sa chair blanche et délicate attire les amateurs de fruits tropicaux japonais ou malaisiens.',
          facts: ['Le mangoustan est connu pour ses couleurs contrastées et sa saveur douce.', 'Sa chair est souvent consommée froide.'],
          image: 'https://images.unsplash.com/photo-1498837167922-ddd27525d352?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1498837167922-ddd27525d352?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1502741338009-cac2772e18bc?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le mangoustan est un parfum de tropicalité dans une peau violette. Il appartient aux fruits les plus singuliers du monde.',
          tags: ['Malaisie', 'tropical', 'fraîcheur'],
          difficulty: 'Facile',
          prepTime: '5 min',
          cookTime: '0 min',
          animation: 'Éclat de chair blanche sur fond violet',
        })
      ]
    },
    {
      id: 'salle-9',
      name: 'Salle 9 – Légumes et plantes comestibles',
      theme: 'Légumes',
      decor: 'Jardins d’ombre, lumière verte et mannequins végétaux',
      palette: '#8fd17f',
      mood: 'frais, soigné, nourrissant',
      guide: 'Les légumes comme œuvres des jardins.',
      exhibits: [
        createExhibit({
          id: 'fennel',
          name: 'Fenouil',
          category: 'Plante aromatique',
          country: 'Italie',
          region: 'Méditerranée',
          description: 'Une plante aromatique aux saveurs anisées, utilisée en salade, potage, poisson et sauce.',
          origin: 'Le fenouil est largement cultivé dans les régions méditerranéennes.',
          ingredients: ['fenouil', 'huile d’olive', 'citron', 'sel'],
          method: 'Le bulbe et les feuilles sont consommés frais ou cuits selon les recettes.',
          culturalNotes: 'Le fenouil séduit par son goût équilibré et sa fraîcheur de l’été.',
          anecdote: 'On l’utilise autant comme légume que pour son parfum d’anis.',
          facts: ['Le fenouil est un légume aromatique de la famille des apiacées.', 'Le goût est plus doux après cuisson.'],
          image: 'https://images.unsplash.com/photo-1464226184884-fa52ac9c0d0f?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1464226184884-fa52ac9c0d0f?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1542838132-92c53300491e?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le fenouil est un légume de finesse. Son parfum d’anis et sa fraîcheur le rendent immédiatement reconnaissable.',
          tags: ['Méditerranée', 'aromatique', 'légume'],
          difficulty: 'Facile',
          prepTime: '10 min',
          cookTime: '15 min',
          animation: 'Feuilles qui s’ouvrent et lumière verte',
        }),
        createExhibit({
          id: 'kale',
          name: 'Kale',
          category: 'Légume vert',
          country: 'Royaume-Uni',
          region: 'Europe',
          description: 'Une feuille verte robuste, utilisée dans les salades, soupes et cuissons chaudes.',
          origin: 'Le kale est une plante de la famille des choux, cultivée dans plusieurs régions d’Europe.',
          ingredients: ['kale', 'huile d’olive', 'citron', 'ail'],
          method: 'Les feuilles sont blanchies, cuisinées ou déchirées dans des salades.',
          culturalNotes: 'Le kale représente le versant sain et intense des légumes verts.',
          anecdote: 'Son goût est plus fort que celui d’une laitue classique et plus résistant à la cuisson.',
          facts: ['Le kale est riche en nutriments.', 'Il se conserve bien et supporte le froid.'],
          image: 'https://images.unsplash.com/photo-1542838132-92c53300491e?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1542838132-92c53300491e?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1464226184884-fa52ac9c0d0f?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le kale est un légume robuste qui apporte une vraie présence verte à la table.',
          tags: ['Europe', 'vert', 'nutrition'],
          difficulty: 'Facile',
          prepTime: '10 min',
          cookTime: '15 min',
          animation: 'Feuilles qui se courbent sous la lumière',
        }),
        createExhibit({
          id: 'salsify',
          name: 'Salsifis',
          category: 'Racine ancienne',
          country: 'France',
          region: 'France rurale',
          description: 'Une racine au goût de noisette, autrefois appréciée dans les cuisines de terroir.',
          origin: 'Le salsifis est un légume ancien, généralement cultivé dans les jardins traditionnels.',
          ingredients: ['salsifis', 'beurre', 'citron', 'sel'],
          method: 'La racine est lavée puis cuite doucement avant d’être servie avec beurre et aromates.',
          culturalNotes: 'Il évoque une cuisine du passé, plus rustique et attentive aux saisons.',
          anecdote: 'Le salsifis est souvent présenté comme l’un des légumes oubliés des jardins français.',
          facts: ['Il est parfois consommé sous forme de potage ou de gratin.', 'Son goût est plus doux après cuisson.'],
          image: 'https://images.unsplash.com/photo-1461354464878-ad92f492a5a0?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1461354464878-ad92f492a5a0?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1542838132-92c53300491e?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le salsifis est une racine de terroir aux saveurs fines. C’est un légume ancien, souvent oublié mais plein de charme.',
          tags: ['France', 'racine', 'terroir'],
          difficulty: 'Moyenne',
          prepTime: '15 min',
          cookTime: '25 min',
          animation: 'Lumière délicate sur la racine',
        })
      ]
    },
    {
      id: 'salle-10',
      name: 'Salle 10 – Champignons et trésors de la nature',
      theme: 'Champignons',
      decor: 'Forêt sombre, lumière verte, vitrines humides',
      palette: '#d9b782',
      mood: 'naturel, mystérieux, forestier',
      guide: 'Le monde végétal souterrain et forestier.',
      exhibits: [
        createExhibit({
          id: 'shiitake',
          name: 'Shiitake',
          category: 'Champignon cultivé',
          country: 'Japon',
          region: 'Asie orientale',
          description: 'Un champignon aux chapeaux brun foncé et au goût umami profond, très présent dans les cuisines asiatiques.',
          origin: 'Le shiitake existe depuis des siècles dans les cultures asiatiques et dans la cuisine traditionnelle.',
          ingredients: ['shiitake', 'soja', 'ail', 'huile'],
          method: 'Le champignon est sauté, mijoté ou séché pour intensifier son parfum.',
          culturalNotes: 'Il est très apprécié pour sa texture souple et sa richesse aromatique.',
          anecdote: 'La culture du shiitake est ancrée dans les traditions forestières de l’Asie.',
          facts: ['Il est souvent utilisé dans les bouillons et les plats mijotés.', 'Ses champignons peuvent être consommés frais ou séchés.'],
          image: 'https://images.unsplash.com/photo-1501004318641-b39e6451bec6?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1501004318641-b39e6451bec6?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1471193945509-9ad0617afabf?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'Le shiitake est un champignon aux formes élégantes et au goût profond. Il apporte à la cuisine une vraie richesse umami.',
          tags: ['Japon', 'champignon', 'umami'],
          difficulty: 'Facile',
          prepTime: '10 min',
          cookTime: '15 min',
          animation: 'Champignon qui gonfle et senteur de forêt',
        }),
        createExhibit({
          id: 'morille',
          name: 'Morille',
          category: 'Champignon forestier',
          country: 'France',
          region: 'Massif central',
          description: 'Un champignon très prisé, reconnaissable à son aspect alvéolé, au goût de terre et de bois.',
          origin: 'La morille est un champignon de printemps très apprécié dans la gastronomie française et européenne.',
          ingredients: ['morilles', 'beurre', 'ail', 'crème'],
          method: 'Le champignon est nettoyé, sauté puis accompagné d’une sauce légère ou d’une garniture.',
          culturalNotes: 'Sa présence dans les forêts de montagne lui donne une aura presque prestigieuse.',
          anecdote: 'Les morilles sont souvent recherchées au printemps dans les sous-bois.',
          facts: ['La morille doit être correctement nettoyée avant la cuisson.', 'Son goût est très particulier et très recherché.'],
          image: 'https://images.unsplash.com/photo-1471193945509-9ad0617afabf?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1471193945509-9ad0617afabf?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1501004318641-b39e6451bec6?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La morille est un champignon prestigieux : alvéolé, forestier et délicat. Il raconte le mystère des sous-bois.',
          tags: ['France', 'forêt', 'champignon'],
          difficulty: 'Moyenne',
          prepTime: '15 min',
          cookTime: '20 min',
          animation: 'Éclat de lumière sur champignons alvéolés',
        }),
        createExhibit({
          id: 'truffle',
          name: 'Truffe',
          category: 'Champignon rare',
          country: 'France',
          region: 'Périgord',
          description: 'Un champignon souterrain aux arômes intenses, recherché pour sa valeur culinaire et sa rareté.',
          origin: 'La truffe est l’un des trésors des forêts méditerranéennes et de certaines zones d’Europe.',
          ingredients: ['truffe', 'beurre', 'œufs', 'crème', 'riz'],
          method: 'La truffe est râpée ou finement coupée pour parfumer des préparations fines.',
          culturalNotes: 'La truffe symbolise la recherche, la patience et le luxe discret.',
          anecdote: 'Sa récolte est souvent associée à des traditions très spécifiques et à un savoir-faire ancien.',
          facts: ['La truffe se développe dans des sols très particuliers.', 'Ses arômes peuvent être très puissants.'],
          image: 'https://images.unsplash.com/photo-1501004318641-b39e6451bec6?auto=format&fit=crop&w=1200&q=80',
          images: [
            'https://images.unsplash.com/photo-1501004318641-b39e6451bec6?auto=format&fit=crop&w=1200&q=80',
            'https://images.unsplash.com/photo-1471193945509-9ad0617afabf?auto=format&fit=crop&w=1200&q=80'
          ],
          voiceText: 'La truffe est l’un des rameaux les plus singuliers du monde culinaire. Son parfum est profond, rare et de grande élégance.',
          tags: ['France', 'truffe', 'rare'],
          difficulty: 'Moyenne',
          prepTime: '15 min',
          cookTime: '10 min',
          animation: 'Râpage fin et parfum intense',
        })
      ]
    }
  ];

  return {
    id: 'museum-main',
    name: 'Le Musée des Merveilles',
    rooms,
  };
}

const defaultQuiz = [
  {
    question: 'Quel plat est mythique en France et se sert avec un bouillon ?',
    options: ['Pot-au-feu', 'Ratatouille', 'Couscous', 'Tacos'],
    answer: 'Pot-au-feu',
    explanation: 'Le pot-au-feu est un grand classique de la cuisine française, apprécié pour son bouillon et sa simplicité.',
  },
  {
    question: 'Quel pays est associé à la paella ?',
    options: ['Espagne', 'Italie', 'Mexique', 'Japon'],
    answer: 'Espagne',
    explanation: 'La paella est emblématique de la cuisine espagnole, surtout de Valence.',
  },
  {
    question: 'Quel fruit est célèbre pour son odeur marquée ?',
    options: ['Durian', 'Mangue', 'Pomme', 'Poire'],
    answer: 'Durian',
    explanation: 'Le durian est connu pour son odeur très forte, qui le rend si particulier.',
  },
  {
    question: 'Quel dessert est réalisé avec des feuilles de pâte phyllo ?',
    options: ['Baklava', 'Crème brûlée', 'Panna cotta', 'Cheesecake'],
    answer: 'Baklava',
    explanation: 'La baklava est une pâtisserie feuilletée avec noix et sirop, typique de plusieurs cuisines du Moyen-Orient.',
  },
  {
    question: 'Le bibimbap est typique de quelle cuisine ?',
    options: ['Corée', 'Égypte', 'Inde', 'Brésil'],
    answer: 'Corée',
    explanation: 'Le bibimbap est un bol de riz coréen avec légumes, viande et sauce épicée.',
  }
];

function buildSessionState() {
  return {
    progress: 0,
    sessionHistory: [],
    stats: {
      roomsVisited: 0,
      exhibitsSeen: 0,
      quizAnswers: 0,
      goodQuizAnswers: 0,
    },
    favorites: [],
  };
}

function loadMuseum() {
  const raw = localStorage.getItem(STORAGE_KEY);
  if (!raw) {
    const initial = defaultMuseum();
    localStorage.setItem(STORAGE_KEY, JSON.stringify(initial));
    return initial;
  }

  try {
    const parsed = JSON.parse(raw);
    if (!parsed.rooms || !Array.isArray(parsed.rooms)) throw new Error('Invalid museum data');
    return parsed;
  } catch (error) {
    const initial = defaultMuseum();
    localStorage.setItem(STORAGE_KEY, JSON.stringify(initial));
    return initial;
  }
}

function saveMuseum() {
  localStorage.setItem(STORAGE_KEY, JSON.stringify(state.museum));
}

function loadSessionState() {
  const raw = localStorage.getItem(SESSION_KEY);
  if (!raw) {
    const initial = buildSessionState();
    localStorage.setItem(SESSION_KEY, JSON.stringify(initial));
    return initial;
  }

  try {
    const parsed = JSON.parse(raw);
    return parsed;
  } catch (error) {
    const initial = buildSessionState();
    localStorage.setItem(SESSION_KEY, JSON.stringify(initial));
    return initial;
  }
}

function saveSessionState() {
  localStorage.setItem(SESSION_KEY, JSON.stringify(state.session));
}

const state = {
  museum: loadMuseum(),
  session: loadSessionState(),
  currentRoomIndex: 0,
  currentExhibitIndex: 0,
  selectedImageIndex: 0,
  autoTour: false,
  autoInterval: null,
  currentVoice: null,
  quizIndex: 0,
  quizAnswered: false,
};

function getCurrentRoom() {
  return state.museum.rooms[state.currentRoomIndex] || state.museum.rooms[0];
}

function getCurrentExhibit() {
  const room = getCurrentRoom();
  return room.exhibits[state.currentExhibitIndex] || room.exhibits[0];
}

function updateProgress(value) {
  state.session.progress = Math.max(0, Math.min(100, value));
  saveSessionState();
  const progressBar = document.getElementById('progress-fill');
  if (progressBar) {
    progressBar.style.width = `${state.session.progress}%`;
  }
}

function recordVisit() {
  state.session.stats.exhibitsSeen += 1;
  if (!state.session.sessionHistory.includes(`${state.currentRoomIndex}:${state.currentExhibitIndex}`)) {
    state.session.sessionHistory.push(`${state.currentRoomIndex}:${state.currentExhibitIndex}`);
  }
  saveSessionState();
}

function setRoom(index) {
  state.currentRoomIndex = index;
  const room = getCurrentRoom();
  state.currentExhibitIndex = 0;
  state.selectedImageIndex = 0;
  recordVisit();
  renderPublicPage();
}

function setExhibit(index) {
  state.currentExhibitIndex = index;
  state.selectedImageIndex = 0;
  recordVisit();
  renderPublicPage();
}

function nextExhibit() {
  const room = getCurrentRoom();
  const nextIndex = (state.currentExhibitIndex + 1) % room.exhibits.length;
  state.currentExhibitIndex = nextIndex;
  state.selectedImageIndex = 0;
  recordVisit();
  renderPublicPage();
}

function nextRoom() {
  const nextRoomIndex = (state.currentRoomIndex + 1) % state.museum.rooms.length;
  state.currentRoomIndex = nextRoomIndex;
  state.currentExhibitIndex = 0;
  state.selectedImageIndex = 0;
  recordVisit();
  renderPublicPage();
}

function startAutoTour() {
  state.autoTour = !state.autoTour;
  if (state.autoTour) {
    state.autoInterval = setInterval(() => {
      nextExhibit();
      if (state.currentExhibitIndex === 0) {
        nextRoom();
      }
    }, 7000);
  } else {
    clearInterval(state.autoInterval);
  }
  renderPublicPage();
}

function speakNarration() {
  const exhibit = getCurrentExhibit();
  if (!('speechSynthesis' in window)) {
    alert('La synthèse vocale n’est pas disponible dans ce navigateur. Le texte sera affiché, mais la voix automatique ne peut pas jouer.');
    return;
  }

  window.speechSynthesis.cancel();
  const utterance = new SpeechSynthesisUtterance(exhibit.voiceText || exhibit.description);
  const voices = window.speechSynthesis.getVoices();
  const selected = document.getElementById('voice-select')?.value;
  if (selected) {
    const voice = voices.find((item) => item.name === selected);
    if (voice) utterance.voice = voice;
  }
  utterance.rate = Number(document.getElementById('voice-rate')?.value || '1');
  utterance.pitch = 1.1;
  utterance.volume = 1;
  window.speechSynthesis.speak(utterance);
}

function repeatNarration() {
  speakNarration();
}

function stopVoice() {
  if ('speechSynthesis' in window) {
    window.speechSynthesis.cancel();
  }
}

function renderVoiceOptions() {
  const select = document.getElementById('voice-select');
  if (!select) return;

  if ('speechSynthesis' in window) {
    const voices = window.speechSynthesis.getVoices();
    select.innerHTML = voices.length
      ? voices.map((voice) => `<option value="${voice.name}">${voice.name}</option>`).join('')
      : '<option value="default">Voix système</option>';
  } else {
    select.innerHTML = '<option value="default">Voix indisponible</option>';
  }
}

function renderPublicPage() {
  const room = getCurrentRoom();
  const exhibit = getCurrentExhibit();
  const rooms = state.museum.rooms;

  const roomList = document.getElementById('room-list');
  if (roomList) {
    roomList.innerHTML = rooms.map((item, index) => `
      <button class="room-card ${state.currentRoomIndex === index ? 'active' : ''}" data-room-index="${index}">
        <h3>${item.name}</h3>
        <small>${item.exhibits.length} expositions</small>
      </button>
    `).join('');
  }

  const roomCount = document.getElementById('room-count');
  if (roomCount) roomCount.textContent = `${rooms.length}`;

  const currentRoomName = document.getElementById('current-room-name');
  if (currentRoomName) currentRoomName.textContent = room.name;

  const exhibitList = document.getElementById('exhibit-list');
  if (exhibitList) {
    exhibitList.innerHTML = room.exhibits.map((item, index) => `
      <button class="exhibit-card ${state.currentExhibitIndex === index ? 'active' : ''}" data-exhibit-index="${index}">
        <h3>${item.name}</h3>
        <small>${item.category}</small>
      </button>
    `).join('');
  }

  const exhibitCount = document.getElementById('exhibit-count');
  if (exhibitCount) exhibitCount.textContent = `${room.exhibits.length}`;

  const hero = document.getElementById('hero-card');
  if (hero) {
    const images = exhibit.images && exhibit.images.length ? exhibit.images : [exhibit.image];
    const image = images[state.selectedImageIndex] || images[0];
    hero.innerHTML = `
      <img class="hero-image" src="${image}" alt="${exhibit.name}" />
      <div class="hero-overlay"></div>
      <div class="hero-copy">
        <p class="eyebrow">${exhibit.country}</p>
        <h3>${exhibit.name}</h3>
        <p>${exhibit.description}</p>
      </div>
    `;
  }

  const gallery = document.getElementById('gallery-strip');
  if (gallery) {
    const images = exhibit.images && exhibit.images.length ? exhibit.images : [exhibit.image];
    gallery.innerHTML = images.map((image, index) => `
      <button class="gallery-thumb ${state.selectedImageIndex === index ? 'active' : ''}" data-image-index="${index}">
        <img src="${image}" alt="${exhibit.name} ${index + 1}" />
      </button>
    `).join('');
  }

  const metaCategory = document.getElementById('exhibit-category');
  const metaCountry = document.getElementById('exhibit-country');
  const metaName = document.getElementById('exhibit-name');
  const metaDescription = document.getElementById('exhibit-description');
  const metaFacts = document.getElementById('exhibit-facts');
  const metaDetails = document.getElementById('exhibit-details');

  if (metaCategory) metaCategory.textContent = exhibit.category;
  if (metaCountry) metaCountry.textContent = exhibit.country;
  if (metaName) metaName.textContent = exhibit.name;
  if (metaDescription) metaDescription.textContent = exhibit.description;

  if (metaFacts) {
    metaFacts.innerHTML = exhibit.facts.map((fact) => `<li>${fact}</li>`).join('');
  }

  if (metaDetails) {
    metaDetails.innerHTML = `
      <div>
        <dt>Région</dt>
        <dd>${exhibit.region}</dd>
      </div>
      <div>
        <dt>Ingrédients</dt>
        <dd>${exhibit.ingredients.join(', ')}</dd>
      </div>
      <div>
        <dt>Préparation</dt>
        <dd>${exhibit.method}</dd>
      </div>
      <div>
        <dt>Historique</dt>
        <dd>${exhibit.origin}</dd>
      </div>
      <div>
        <dt>Culture</dt>
        <dd>${exhibit.culturalNotes}</dd>
      </div>
    `;
  }

  updateProgress(state.session.progress + 2);
  renderQuiz();
  renderVoiceOptions();

  const toggleButton = document.querySelector('[data-action="toggle-auto"]');
  if (toggleButton) {
    toggleButton.textContent = state.autoTour ? 'Pause de visite' : 'Démarrer la visite';
  }
}

function renderQuiz() {
  const quizCard = document.getElementById('quiz-card');
  if (!quizCard) return;

  const question = defaultQuiz[state.quizIndex % defaultQuiz.length];
  quizCard.classList.add('visible');
  quizCard.innerHTML = `
    <h4>Quiz gourmand</h4>
    <p>${question.question}</p>
    <div class="quiz-options">
      ${question.options.map((option, index) => `
        <button class="quiz-option" data-quiz-option="${option}">${option}</button>
      `).join('')}
    </div>
  `;
}

function answerQuiz(option) {
  const question = defaultQuiz[state.quizIndex % defaultQuiz.length];
  const isCorrect = option === question.answer;
  state.session.stats.quizAnswers += 1;
  if (isCorrect) state.session.stats.goodQuizAnswers += 1;
  state.quizIndex = (state.quizIndex + 1) % defaultQuiz.length;
  state.quizAnswered = true;
  saveSessionState();

  const quizCard = document.getElementById('quiz-card');
  if (!quizCard) return;

  const buttons = [...quizCard.querySelectorAll('.quiz-option')];
  buttons.forEach((button) => {
    const value = button.dataset.quizOption;
    button.disabled = true;
    button.classList.add(value === question.answer ? 'correct' : 'wrong');
    if (value === option && !isCorrect) button.classList.add('wrong');
  });

  const explanation = document.createElement('p');
  explanation.textContent = `${question.explanation} ${isCorrect ? 'Bonne réponse !' : `Bonne réponse : ${question.answer}.`}`;
  quizCard.appendChild(explanation);

  setTimeout(() => {
    renderQuiz();
  }, 2500);
}

function renderAdminPage() {
  const roomList = document.getElementById('admin-room-list');
  const form = document.getElementById('admin-form');
  if (!roomList || !form) return;

  const currentRoom = state.museum.rooms[state.currentRoomIndex] || state.museum.rooms[0];
  const currentExhibit = currentRoom.exhibits[state.currentExhibitIndex] || currentRoom.exhibits[0];

  roomList.innerHTML = state.museum.rooms.map((room, index) => `
    <button class="admin-room-item ${state.currentRoomIndex === index ? 'active' : ''}" data-room-select="${index}">
      <h3>${room.name}</h3>
      <small>${room.exhibits.length} expositions</small>
    </button>
  `).join('');

  form.innerHTML = `
    <div class="form-grid">
      <div class="form-field">
        <label>Nom de la salle</label>
        <input id="room-name" value="${escapeHtml(currentRoom.name)}" />
      </div>
      <div class="form-field">
        <label>Thème</label>
        <input id="room-theme" value="${escapeHtml(currentRoom.theme || '')}" />
      </div>
      <div class="form-field">
        <label>Palette</label>
        <input id="room-palette" type="color" value="${currentRoom.palette || '#d9b35d'}" />
      </div>
      <div class="form-field">
        <label>Décor</label>
        <input id="room-decor" value="${escapeHtml(currentRoom.decor || '')}" />
      </div>
      <div class="form-field">
        <label>Guide</label>
        <input id="room-guide" value="${escapeHtml(currentRoom.guide || '')}" />
      </div>
      <div class="form-field">
        <label>Ambiance</label>
        <input id="room-mood" value="${escapeHtml(currentRoom.mood || '')}" />
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Exposition sélectionnée</label>
        <select id="exhibit-select">
          ${currentRoom.exhibits.map((exhibit, index) => `
            <option value="${index}" ${index === state.currentExhibitIndex ? 'selected' : ''}>${escapeHtml(exhibit.name)}</option>
          `).join('')}
        </select>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Nom</label>
        <input id="exhibit-name" value="${escapeHtml(currentExhibit.name)}" />
      </div>
      <div class="form-field">
        <label>Catégorie</label>
        <input id="exhibit-category" value="${escapeHtml(currentExhibit.category)}" />
      </div>
      <div class="form-field">
        <label>Pays</label>
        <input id="exhibit-country" value="${escapeHtml(currentExhibit.country)}" />
      </div>
      <div class="form-field">
        <label>Région</label>
        <input id="exhibit-region" value="${escapeHtml(currentExhibit.region)}" />
      </div>
      <div class="form-field">
        <label>Image principale</label>
        <input id="exhibit-image" value="${escapeHtml(currentExhibit.image)}" />
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Description</label>
        <textarea id="exhibit-description">${escapeHtml(currentExhibit.description)}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Origine</label>
        <textarea id="exhibit-origin">${escapeHtml(currentExhibit.origin)}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Ingrédients</label>
        <textarea id="exhibit-ingredients">${escapeHtml((currentExhibit.ingredients || []).join(', '))}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Préparation</label>
        <textarea id="exhibit-method">${escapeHtml(currentExhibit.method)}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Culture</label>
        <textarea id="exhibit-cultural">${escapeHtml(currentExhibit.culturalNotes)}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Anecdote</label>
        <textarea id="exhibit-anecdote">${escapeHtml(currentExhibit.anecdote)}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Faits</label>
        <textarea id="exhibit-facts">${escapeHtml((currentExhibit.facts || []).join(' | '))}</textarea>
      </div>
      <div class="form-field" style="grid-column: 1 / -1;">
        <label>Texte vocal</label>
        <textarea id="exhibit-voice">${escapeHtml(currentExhibit.voiceText)}</textarea>
      </div>
    </div>
    <div class="form-actions">
      <button data-action="save-room" class="secondary">Enregistrer la salle</button>
      <button data-action="save-exhibit" class="primary">Enregistrer l’exposition</button>
      <button data-action="add-exhibit" class="secondary">Ajouter une exposition</button>
      <button data-action="delete-exhibit" class="ghost danger">Supprimer l’exposition</button>
    </div>
  `;
}

function saveRoomAndExhibit() {
  const currentRoom = state.museum.rooms[state.currentRoomIndex];
  const currentExhibit = currentRoom.exhibits[state.currentExhibitIndex] || currentRoom.exhibits[0];

  currentRoom.name = document.getElementById('room-name')?.value || currentRoom.name;
  currentRoom.theme = document.getElementById('room-theme')?.value || currentRoom.theme;
  currentRoom.palette = document.getElementById('room-palette')?.value || currentRoom.palette;
  currentRoom.decor = document.getElementById('room-decor')?.value || currentRoom.decor;
  currentRoom.guide = document.getElementById('room-guide')?.value || currentRoom.guide;
  currentRoom.mood = document.getElementById('room-mood')?.value || currentRoom.mood;

  currentExhibit.name = document.getElementById('exhibit-name')?.value || currentExhibit.name;
  currentExhibit.category = document.getElementById('exhibit-category')?.value || currentExhibit.category;
  currentExhibit.country = document.getElementById('exhibit-country')?.value || currentExhibit.country;
  currentExhibit.region = document.getElementById('exhibit-region')?.value || currentExhibit.region;
  currentExhibit.image = document.getElementById('exhibit-image')?.value || currentExhibit.image;
  currentExhibit.description = document.getElementById('exhibit-description')?.value || currentExhibit.description;
  currentExhibit.origin = document.getElementById('exhibit-origin')?.value || currentExhibit.origin;
  currentExhibit.method = document.getElementById('exhibit-method')?.value || currentExhibit.method;
  currentExhibit.culturalNotes = document.getElementById('exhibit-cultural')?.value || currentExhibit.culturalNotes;
  currentExhibit.anecdote = document.getElementById('exhibit-anecdote')?.value || currentExhibit.anecdote;
  currentExhibit.voiceText = document.getElementById('exhibit-voice')?.value || currentExhibit.voiceText;
  currentExhibit.ingredients = (document.getElementById('exhibit-ingredients')?.value || '')
    .split(',')
    .map((item) => item.trim())
    .filter(Boolean);
  currentExhibit.facts = (document.getElementById('exhibit-facts')?.value || '')
    .split('|')
    .map((item) => item.trim())
    .filter(Boolean);
  currentExhibit.images = [currentExhibit.image];

  saveMuseum();
  renderPublicPage();
  renderAdminPage();
}

function addRoom() {
  const newRoom = {
    id: uid('room'),
    name: `Salle ${state.museum.rooms.length + 1}`,
    theme: 'Nouvelle thématique',
    decor: 'Décor à personnaliser',
    palette: '#d9b35d',
    guide: 'À compléter',
    mood: 'À définir',
    exhibits: [createExhibit({
      name: 'Nouvelle exposition',
      category: 'Catégorie',
      country: 'Monde',
      region: 'Région',
      description: 'Description de l’exposition.',
      origin: 'Origine à compléter.',
      ingredients: ['À préciser'],
      method: 'Méthode à compléter.',
      culturalNotes: 'Contexte culturel à compléter.',
      anecdote: 'Anecdote à compléter.',
      facts: ['Fait intéressant.'],
      voiceText: 'Présentation à compléter.',
    })],
  };
  state.museum.rooms.push(newRoom);
  state.currentRoomIndex = state.museum.rooms.length - 1;
  state.currentExhibitIndex = 0;
  saveMuseum();
  renderAdminPage();
  renderPublicPage();
}

function addExhibit() {
  const room = state.museum.rooms[state.currentRoomIndex];
  const newExhibit = createExhibit({
    name: `Nouvelle exposition ${room.exhibits.length + 1}`,
    category: 'Nouvelle catégorie',
    country: 'Monde',
    description: 'Description à compléter.',
    origin: 'Origine à compléter.',
    ingredients: ['Ingrédient'],
    method: 'Méthode à compléter.',
    culturalNotes: 'Détails culturels à compléter.',
    anecdote: 'Anecdote à compléter.',
    facts: ['Fait intéressant.'],
    voiceText: 'Présentation à compléter.',
  });
  room.exhibits.push(newExhibit);
  state.currentExhibitIndex = room.exhibits.length - 1;
  saveMuseum();
  renderAdminPage();
  renderPublicPage();
}

function deleteExhibit() {
  const room = state.museum.rooms[state.currentRoomIndex];
  if (room.exhibits.length === 1) {
    alert('Une salle doit conserver au moins une exposition.');
    return;
  }
  room.exhibits.splice(state.currentExhibitIndex, 1);
  state.currentExhibitIndex = Math.max(0, state.currentExhibitIndex - 1);
  saveMuseum();
  renderAdminPage();
  renderPublicPage();
}

function exportJson() {
  const output = document.getElementById('json-output');
  if (!output) return;
  output.value = JSON.stringify(state.museum, null, 2);
}

function importJson() {
  const output = document.getElementById('json-output');
  if (!output || !output.value.trim()) return;
  try {
    const parsed = JSON.parse(output.value);
    if (!parsed.rooms || !Array.isArray(parsed.rooms)) throw new Error('Format JSON invalide');
    state.museum = parsed;
    state.currentRoomIndex = 0;
    state.currentExhibitIndex = 0;
    saveMuseum();
    renderPublicPage();
    renderAdminPage();
  } catch (error) {
    alert('Le JSON importé est invalide.');
  }
}

function resetSession() {
  state.session = buildSessionState();
  saveSessionState();
  updateProgress(0);
  renderPublicPage();
}

function escapeHtml(value) {
  return String(value)
    .replace(/&/g, '&amp;')
    .replace(/</g, '&lt;')
    .replace(/>/g, '&gt;')
    .replace(/"/g, '&quot;')
    .replace(/'/g, '&#039;');
}

function bindPublicUI() {
  document.addEventListener('click', (event) => {
    const roomButton = event.target.closest('[data-room-index]');
    if (roomButton) {
      setRoom(Number(roomButton.dataset.roomIndex));
      return;
    }

    const exhibitButton = event.target.closest('[data-exhibit-index]');
    if (exhibitButton) {
      setExhibit(Number(exhibitButton.dataset.exhibitIndex));
      return;
    }

    const imageButton = event.target.closest('[data-image-index]');
    if (imageButton) {
      state.selectedImageIndex = Number(imageButton.dataset.imageIndex);
      renderPublicPage();
      return;
    }

    const quizButton = event.target.closest('[data-quiz-option]');
    if (quizButton) {
      answerQuiz(quizButton.dataset.quizOption);
      return;
    }

    const action = event.target.closest('[data-action]');
    if (!action) return;

    switch (action.dataset.action) {
      case 'toggle-auto':
        startAutoTour();
        break;
      case 'next-room':
        nextRoom();
        break;
      case 'speak':
        speakNarration();
        break;
      case 'repeat':
        repeatNarration();
        break;
      case 'pause-voice':
        stopVoice();
        break;
      default:
        break;
    }
  });
}

function bindAdminUI() {
  document.addEventListener('click', (event) => {
    const roomSelect = event.target.closest('[data-room-select]');
    if (roomSelect) {
      state.currentRoomIndex = Number(roomSelect.dataset.roomSelect);
      state.currentExhibitIndex = 0;
      renderAdminPage();
      return;
    }

    const action = event.target.closest('[data-action]');
    if (!action) return;

    switch (action.dataset.action) {
      case 'add-room':
        addRoom();
        break;
      case 'save-room':
      case 'save-exhibit':
        saveRoomAndExhibit();
        break;
      case 'add-exhibit':
        addExhibit();
        break;
      case 'delete-exhibit':
        deleteExhibit();
        break;
      case 'export-json':
        exportJson();
        break;
      case 'import-json':
        importJson();
        break;
      case 'reset-session':
        resetSession();
        break;
      default:
        break;
    }
  });

  document.addEventListener('change', (event) => {
    const exhibitSelect = event.target.id === 'exhibit-select';
    if (exhibitSelect) {
      state.currentExhibitIndex = Number(event.target.value);
      renderAdminPage();
    }
  });
}

function init() {
  const page = document.body.dataset.page;
  if (page === 'public') {
    bindPublicUI();
    renderPublicPage();
    renderVoiceOptions();
  }

  if (page === 'admin') {
    bindAdminUI();
    renderAdminPage();
    exportJson();
  }
}

init();
