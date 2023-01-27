class Territory:

    def __init__(self, name, neighbors, color = None):

        self.name      = name
        self.neighbors = neighbors
        self.color     = color

    def __str__(self):
        return str((self.name, self.neighbors, self.color))


class MapColor:

    def __init__(self, graph, colors):

        self.map     = graph
        self.colors  = colors
        self.vars    = list(self.map.keys())
        self.domains = { var: set(self.colors) for var in self.vars }
